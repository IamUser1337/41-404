In some business situations, you might have data coming from outside sources through connectors, and this data goes into services that hold your important business information. When it comes to Data Loss Prevention (DLP) policies, they usually require both these connectors to talk to each other. The tricky part is making sure that the connectors only talk in one direction and that your valuable business data doesn't accidentally go outside to a third party. We call this managing the flow of data, like making sure it only goes where it's supposed to—this is called **directional data governance.**

Right now, DLP policies don't automatically handle directional data governance. But don't worry, you can use Power Automate to catch and stop any flows that try to send your business data to external places.

Here's an example: Let's say your organization wants to use SharePoint to keep track of Twitter data. The concern here's that private info could end up going from SharePoint to Twitter.

To make sure your data only moves in the right direction, you start by creating a DLP policy in the Power Platform admin center. In this policy, you group together the SharePoint and Twitter connectors as **Business data.** This way, you let people create flows using both these connectors, but you're also making sure that your data stays safe and doesn't accidentally end up in the wrong hands.

1. The first step in accomplishing directional data governance is to create a DLP policy, from the [Power Platform admin center](https://admin.powerplatform.microsoft.com/?azure-portal=true) that includes the SharePoint and Twitter connectors in the **Business** data group. By using this configuration, you're allowing makers to build flows that include both of these connectors.

	![Screenshot of Microsoft Power Platform Admin center Data policies page on the Assign connectors step showing Twitter and SharePoint options.](../media/17-twitter-sharepoint-update.png)

1. Next, you'll transition to the [Power Automate Maker Portal](https://flow.microsoft.com/?azure-portal=true)
and sign in by using your administrator account so you can build your governance flow. Your goal is to build
a scheduled flow that will run every hour.

	![Screenshot of Build a scheduled flow with Flow name set to Detect Twitter Actions.](../media/18-new-flow.png)

1. A Recurrence trigger will automatically be added to your flow. You'll now add an **Initialize variable** action to your flow. Name this variable **previousTimestamp** and then include an expression of
**```ticks(addMinutes(utcNow(),-60))```**. This expression will calculate the number of ticks as of 60 minutes ago. The reason for including this expression is that you want to see if any flows have been created or modified since the last time your flow ran, which would have been 60 minutes ago.

	![Screenshot of Power Automate My flows page with the Initialize variable action's Value property with the ticks formula highlighted.](../media/variable.svg)

1. Add another variable called **isFlowAction** that is of type Boolean and has a default value of **false**. You'll use this variable later in your flow when you detect that a flow includes a Twitter action.

	![Screenshot of a second Initialize variable action called Does flow contain Twitter action.](../media/twitter-boolean.svg)

1. Next, use the PowerPlatform for Admins connector and the **List Environments as Admin** action that will provide your flow with a complete list of environments in your tenant. Then, loop through each environment so that you can look for flows that include Twitter actions.

	![Screenshot of new PowerPlatform for Admins action with the List Environments as Admin option highlighted.](../media/list-environments.svg)

1. After listing all environments, you'll add the Flow management connector and use the **List Flows as Admin** action that will provide a listing of all flows for a given environment.

	![Screenshot of Choose an action step with Flow management and List Flows as Admin highlighted.](../media/flow-management.svg)

1. The **List Flows as Admin** action requires the name of an environment as an input parameter. Use the **Name** column that is returned from your **List Environments as Admin** call. When you provide this input, an **Apply to each** action will automatically be added that will allow you to iterate through all environments.

	![Screenshot of Apply to each action with List Flows as Admin with dynamic content Name.](../media/list-flows-admin.svg)

1. Because you're only interested in exploring recently modified flows, you'll add a condition to your flow and will compare the ticks of the flow's last modified timestamp to that of your variable that you
established earlier in your flow. To accomplish this task, use an expression to calculate the ticks of your last modified timestamp. The complete statement is **```ticks(items('Apply_to_each_2')?['properties']?['lastModifiedTime']) is greater than previousTimestamp```**.

	[![Screenshot of condition with number of ticks greater than previous with If yes and If no options.](../media/compare-ticks.svg)](../media/compare-ticks.svg#lightbox)

1. When you detect that a flow has been modified within the past 60 minutes, you'll want to ensure that it doesn't belong to your administrator. This verification will help avoid an error when you try to add the administrator as co-owner of a flow in a future step. To detect if the current flow belongs to your
administrator, use the Office 365 Users connector and the **Get my profile (v2)** action. This step will return information about the user who established a connection to the connector, which in this case is the
administrator. Next, add the Office 365 Users action to the **If yes** branch.

	![Screenshot of Office 365 users in the If yes condition with the Get my profile action highlighted.](../media/users.svg)

1. Now, you'll add another condition that will verify if the **Creator** object ID (from the **List Flows as Admin** action) isn't equal to **ID** (from the **Get my profile (V2)** action). In the **If yes** branch, add the **Edit Flow Owner Role as Admin** action that belongs to the Microsoft Flow for Admins connector. This action will add your administrator user as a co-owner of the flow and will help extract the flow
definition, which requires you to be a co-owner of the flow. You'll retrieve the flow definition in an upcoming step, but for now, provide the current **Environment Name**, current **Flow Name**, and details about your administrator user such as email address, display name, and ID. These values are accessible from your **Get my profile (V2)** action.

	[![Screenshot of EditFlow Owner Role as Admin with properties highlighted.](../media/edit-flow-owners.svg)](../media/edit-flow-owners.svg#lightbox)

1. After you have added your administrator account as a co-owner of the flow, you can call the **Get Flow as Admin** action from the Flow management connector.

	![Screenshot of Flow management with Get Flow as Admin highlighted.](../media/get-flow-admin.svg)

1. The inputs to the **Get Flow as Admin** action includes the current **Environment Name** and **Flow Name**. The output of this action includes the flow definition that will allow you to determine if a Twitter action exists.

	[![Screenshot of If yes condition with Get Flow as Admin added with Environment set to Name and Flow set to Flow Name.](../media/get-flow.svg)](../media/get-flow.svg#lightbox)

1. To check whether a Twitter action is being used, add a
condition to your flow and verify if the **Action Api** name (from the **Get Flow as Admin** action) is equal to *shared_twitter*. After you have added this
condition, an **Apply to each** loop will be applied because the **Action Api** name attribute is part of an array because each flow can have many actions.

1. Within the **If yes** branch, update your  **isFlowAction** variable to be set to **true** because you have now found a flow that includes a Twitter
action. You'll use this variable later in your flow to determine whether you need to disable a flow and send an email to the flow owner.

	[![Screenshot of Condition with If yes with Set variable - Twitter Action exists highlighted.](../media/check-twitter.svg)](../media/check-twitter.svg#lightbox)

1. Outside the **Apply to each** variable that allows you to iterate through all actions in your flow, add another condition. This condition will verify if the value of your **isFlowAction** variable is **true**.

	![Screenshot of Condition 3 - Does Twitter action exist highlighted.](../media/does-twitter-action-exist.svg)

1. In the **If yes** branch, add the Microsoft Flow for Admins connector and then select the **Disable Flow as Admin** action. This action will allow you to disable the flow so that information can't be sent to
Twitter. To call this action, include the current **Environment Name** and **Flow Name**.

	![Screenshot of If yes containing Disable Flow as Admin with Environment Name set to Name and Flow Name set to Flow Name.](../media/disable-flow.svg)

1. When disabling someone's flow, you'll want to send an email to them so they're aware that their flow is no longer running. To get the flow owner's email address, use the Office 365 Users connector and use the **Get
user profile (V2)** action to return the owner's email address. To get their email address, you'll need to add the **Creator object ID**, which can be retrieved from the **List Flows as Admin** action.

	![Screenshot of Get user profile - Flow Creator with User (UPN) set to the Creator object ID.](../media/get-flow-creator-email.svg)

1. Send an email to the flow owner by using the Office 365 Outlook connector and the **Send an email (V2)** action. Use information that is returned from the **Get user profile (V2)** action to send this email,
including the **Mail** and **Given Name** attributes. In addition, you can include the name of the flow by adding the **Flow Display Name** attribute found in the **List Flows as Admin** output.

	![Screenshot of Send an email with To set to Mail, text in the Subject, and text in the body with Given Name and Flow Display Name fields.](../media/send-email.svg)

1. Because you're looping through all flows in your tenant, you'll need to set your **isFlowAction** variable back to **false** so that you can look for other flows that might have a Twitter action. You can now save your administrative flow.

	![Screenshot of Set variable - Reset Twitter Flag with Name set to isFlowAction and Value set to false.](../media/reset-flag.svg)

1. To test your flow, sign in to the Power Automate maker portal by using a different account. Now, you'll create a flow that includes a SharePoint trigger and a Twitter action. This scenario won't be blocked by your DLP policy, but it should be detected by the
administrative flow that you created.

	![Screenshot of Power Automate on the My Flows page creating a flow with the Twitter action with steps "When an item is created" and Get user profile.](../media/create-flow-twitter-action.svg)

1. Now, you can run your Detect Twitter Actions flow that you previously created as an administrator. When this flow runs, it should detect that a flow was recently modified and that it includes a Twitter action. As a
result, an email will be sent to the flow owner.

	![Screenshot of email with the subject Your flow has been disabled, and the message "Your flow: SharePoint > Twitter has been disabled, et cetera".](../media/40-test-results.png)

1. If you examine the SharePoint to Twitter flow, you'll discover that it has been disabled as a result of your administrator disabling the flow.

	![Screenshot of Power Automate Flows page with the SharePoint > Twitter flow disabled.](../media/disabled.svg)

However, retrieving information from Twitter and sending it to SharePoint doesn't violate your governance rules. As a result, you can create another flow by using your flow maker's account, which includes a Twitter trigger and a SharePoint action. When you run your Detect Twitter Actions governance flow, it remains functional and isn't disabled because this is a permitted use case.

![Screenshot of Power Automate on the My Flows page creating a flow with the Twitter action with steps "When a new tweet is posted" and Create item.](../media/create-flow-twitter-trigger.svg)
