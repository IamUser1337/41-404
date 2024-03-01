In this exercise, you set up live chat for Omnichannel for Dynamics 365 Customer Service. Omnichannel for Customer Service offers a suite of capabilities that extend the power of Dynamics 365 Customer Service Enterprise so that organizations can instantly connect and engage with customers across digital messaging channels.

In this exercise, you complete the following tasks:

1. Assign the Omnichannel agent security role to your user and the bot user.

1. Create an application user with the MCH Application ID and your bot ID.

1. Set up queues for bot and agent users.

1. Set up a workstream to define a chat channel with a context variable and routing rule to route the message to a bot or an agent.

## Task: Assign the Omnichannel agent security role

To assign the Omnichannel agent security role, follow these steps:

1. While in an InPrivate or Incognito browser, go to [Microsoft Power Apps](https://make.powerapps.com/?azure-portal=true).

1. Select your environment from the **Environment** dropdown menu in the upper right.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Environment page navigation bar.](../media/29-environment.png)

1. Select the **gear icon** in the upper-right corner and then select **Advanced settings**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the environment Settings menu with Advance settings selected.](../media/30-advanced-settings.png)](../media/30-advanced-settings.png#lightbox)

1. A new window should open showing the **Business Management** section of Dynamics 365. If loading takes a while, reload the page.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Dynamics 365 Business Management section.](../media/31-business-management.png)](../media/31-business-management.png#lightbox)

1. On the upper command bar next to Dynamics 365, select  **Settings** to open the dropdown menu. Select **Security** in the third column under **System**.
   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Business Management Settings page with the Security option highlighted in the System menu.](../media/32-security-settings.png)](../media/32-security-settings.png#lightbox)

1. Under **Security**, select **Users**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Users option in the Security section.](../media/33-security-users.png)](../media/33-security-users.png#lightbox)

1. Switch the grid view dropdown menu from **Omnichannel Users** to **Enabled Users** so that you can view the user in the list.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Omnichannel Users menu with the Enabled Users option highlighted.](../media/34-enabled-users.png)](../media/34-enabled-users.png#lightbox)

1. In the **Enabled Users** list, scroll or use the search bar to find your user.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of search results in the Enabled Users view.](../media/35-find-user.png)](../media/35-find-user.png#lightbox)

1. Select your user for the training and then select **Manage Roles** on the upper command bar.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of selecting Manage Roles on the command bar after selecting your user.](../media/36-manage-roles.png)](../media/36-manage-roles.png#lightbox)

1. Select the **Omnichannel agent** role to assign to your user and then select **OK**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Manage User Roles dialog with Omnichannel agent selected under the Role Name section.](../media/37-manage-user-roles.png)](../media/37-manage-user-roles.png#lightbox)

You've now assigned the correct Omnichannel agent role to the user, which allows you to be a live agent in Omnichannel.

## Task: Create a Health Bot user in Dynamics 365 Customer Service

You need to set up two users in Omnichannel for Customer Service:

- **Health Bot User** - The Azure Health Bot user that you created in the previous exercise. This configuration allows you to assign the bot as a user and take initial messages through live chat.

- **Omnichannel Agent User** - The current user account that you've used to sign in to Dynamics 365. This configuration allows you to be a live agent in Customer Service who receives messages from portal users through Azure bot escalations.

In this task, you create a bot user, which helps you connect **Azure Health Bot** with **Omnichannel live chat**.

1. Open a new tab and go to [Microsoft Power Platform admin center](https://admin.powerplatform.microsoft.com/?azure-portal=true).

1. Search for and select your Microsoft Cloud for Healthcare environment from the list.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the list of environments.](../media/38-application-users.png)](../media/38-application-users.png#lightbox)

1. On your **Environments > Details** page, select the **Settings** button on the upper command bar.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Settings button on the Environments Details page.](../media/40-application-user.png)](../media/40-application-user.png#lightbox)

1. Expand **Users + permissions** and then select **Application users**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Users and permissions dropdown menu with the Application users option selected.](../media/41-new-user-form.png)](../media/41-new-user-form.png#lightbox)

1. Select the **+ New app user** button to create a new application user.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the New app user button.](../media/42-bot-application-identification.png)](../media/42-bot-application-identification.png#lightbox)

1. Select **+ Add an app** on the **Create a new app user** page.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Add an app option on the Create a new app user page.](../media/44-application-manage-roles.png)](../media/44-application-manage-roles.png#lightbox)

1. Paste the **Application ID** (the Application (client) ID that you obtained in the Azure portal for the supplied MCH Application ID) into the search box and then select the app from the list. You can also search for **mch**. Select **Add**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the application ID settings.](../media/44-omnichannel-agent.png)

1. Select a **Business unit** from the dropdown list (the options in the list are unique for each Dynamics 365 environment). Select **Create** in the lower right of the page.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Create a new app user view.](../media/create-user.png)](../media/create-user.png#lightbox)

1. Return to the **Dynamics 365 User** page that you previously accessed through **Advanced settings**. Switch the view to **Enabled Users** if you're not already on it. Clear the search terms, if any.

1. While in the **Enabled Users** list, search for **MCH Application ID** or scroll to find the bot app user. Double-click the user or select the row and then select **Edit**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the application I D search results.](../media/application-id.png)](../media/application-id.png#lightbox)

1. Above the user name, change the form type from **User** to **Application User**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Application User view selection.](../media/app-user.png)](../media/app-user.png#lightbox)

   A new form appears, and the **User type** is **Application user**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Application User form.](../media/app-user-form.png)](../media/app-user-form.png#lightbox)

1. In the **User Information** section, change the **User type** from **Application user** to **Bot application user**. A new field called **Bot application ID** displays.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Bot application user selection in the User type dropdown menu.](../media/bot-user-id.png)

1. Add your details to the **Bot application ID**. This ID is the Azure Health Bot ID that you previously noted when you enabled the Teams and Omnichannel channels. This field displays after **Bot application user** has been selected as the **User type**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Bot application I D field filled out in the form.](../media/bot-id.png)

1. Select **Manage Roles** on the command bar.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Manage Roles option highlighted on the command bar.](../media/manage-roles.png)](../media/manage-roles.png#lightbox)

1. Assign the **Omnichannel agent** role to the bot user as you did for your own user in the previous task. This action allows the bot to act as an omnichannel agent like your user.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of adding the Omnichannel agent role to the bot user.](../media/37-manage-user-roles.png)

1. Select the **Omnichannel Administrator** role for your user ID and MCH Application ID users.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Omnichannel administrator and agent roles assigned to the bot user.](../media/administrator-agent.png)

You've successfully created a bot user and have assigned the Omnichannel agent role to it.

## Task: Create and set up human agent queues

You can use queues to collect and distribute workload among agents. As a result, agents are added as members to the queues and the workload is distributed among the agents based on assignment methods. For more information, see [Manage queues for unified routing](/dynamics365/customer-service/queues-omnichannel/?azure-portal=true).

In this task, you create the omnichannel queue that's necessary for communicating with a human agent.

1. Switch back to the tab with [Power Apps](https://make.powerapps.com/?azure-portal=true), select **Apps** in the navigation pane, and open the **Customer Service admin center** app.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Apps menu with the Customer Service admin center option selected.](../media/45-customer-service-admin-center.png)](../media/45-customer-service-admin-center.png#lightbox)

1. You should be on the **Home** page. Select **Guided channel setup** on the navigation pane and select **Start new**. You can automatically create a custom chat channel, queue, and workstream to help connect users to bots and human agents.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Customer Service admin center Home page with the Begin button highlighted next to Guided channel setup.](../media/46-homepage.png)](../media/46-homepage.png#lightbox)

1. On the **Name your setup** page, in the **Setup name** field, and enter the name **Healthcare Training**. Select **Next**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Name your setup page, showing the name entered in the Setup name field.](../media/47-setup-name.png)](../media/47-setup-name.png#lightbox)

1. Select **Chat** as the channel type. Select **Next**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Chat category selected for the channel type.](../media/48-channel-type.png)](../media/48-channel-type.png#lightbox)

1. Select **Continue setup** on the **Summary** page.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Summary page for the channel setup.](../media/49-setup-summary.png)](../media/49-setup-summary.png#lightbox)

1. Select **Next** on the following two screens, which discuss creating user accounts and assigning security roles.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of information on creating user accounts.](../media/50-user-accounts.png)](../media/50-user-accounts.png#lightbox)

   > [!div class="mx-imgBorder"]
   > [![Screenshot of information about assigning security roles.](../media/51-security-roles.png)](../media/51-security-roles.png#lightbox)

1. In the **Define a queue** page, create a queue called **Escalate to Human**, which manages and redirects the incoming messages from a user to a Customer Service (human) agent when the bot sends the user through to a live agent. Create the new queue with the following details:

   - **Name** - Escalate to Human
   - **Type** - Defaults to **Messaging**

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Define a queue form.](../media/52-define-queue.png)](../media/52-define-queue.png#lightbox)

1. Select **Next**.

1. Select your user to add to the queue. Select **Next**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of adding your user to the queue.](../media/53-add-users.png)](../media/53-add-users.png#lightbox)

You've now created the necessary queue to escalate to a human agent and have added your user to the messaging queue. Now, you can create the workstream to initially route to a virtual bot, along with routing rules to direct the user to the **Escalate to Human** queue in the proper conditions.

## Task: Update the live workstream with context variables and routing rules

A workstream is a container to enrich, route, and assign work items, and it's associated with a channel, such as live chat, voice, or case. After a bot has been added to a workstream, the incoming work item will be routed to the selected bot at runtime based on classification rules. For more information, see [Create workstreams for unified routing](/dynamics365/customer-service/create-workstreams?azure-portal=true).

In this task, you set up basic chat routing with a new workstream. This setup allows users to chat with a bot user initially and then route to a live human agent in the proper situation.

You complete the following tasks:

- Create a new channel and workstream.

- Turn on proactive chat for the channel.

- Add a bot for initial routing: Initial customer conversation is directed to the Azure Health Bot.

- Create a context variable and routing rule to escalate to a human agent. When context variable **EscalateToAgent** is present and set to **1**, route to the **Escalate to Human** queue that you previously set up with your user so that an agent can continue the conversation.

1. While continuing the guided setup from the previous task, enter a **Chat name** and **Chat language** for your channel and a workstream **Name**. Keep the **Work distribution mode** as **Push** and then select **Next**.

   - **Chat name** -  Chat Widget

   - **Workstream Name** - Chat Workstream

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the create a channel and workstream form.](../media/54-chat-workstream.png)](../media/54-chat-workstream.png#lightbox)

1. Define a ruleset that allows work from this channel to be routed to the **Escalate to Human** queue. Name the **Routing rules** as **Human Agent** and the **Rule item** as **Human Agent Rule**. Select **Next**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the setup page to define a routing ruleset.](../media/55-human-agent-rule.png)](../media/55-human-agent-rule.png#lightbox)

   > [!NOTE]
   > On the **Define a Chatbot** page, select **Skip for now** and select **Next**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the notification that, by default, conditions can't be set and all items are routed to the queue.](../media/55-default-condition.png)](../media/55-default-condition.png#lightbox)

1. It takes a moment for the system to create the chat channel and workstream. When the process is complete, make sure that you **Copy** the **chat widget snippet code** and store it for later. Select **Go to home**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Chat setup complete dialog, showing the Copy button to copy the chat widget snippet code.](../media/56-go-home.png)](../media/56-go-home.png#lightbox)

1. You still need to set up a few components for the routing to happen correctly:

   1. Enable proactive chat for the chat channel so that the bot can prompt the user.

   1. Add the bot user in the default messaging queue so that conversations initially route to the bot.

   1. Add the default messaging queue as the fallback queue for the new workstream.

   1. Define the routing rule in the workstream for escalating to a human agent.

1. Go to **Overview** on the navigation pane. Select **Chat** in the **Channels** section to view all chat channels.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Overview page with the Chat category highlighted in the Channels section.](../media/57-overview-channels.png)](../media/57-overview-channels.png#lightbox)

1. Select the newly created chat channel, **Chat Widget**, and then select **Edit** on the command bar.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Chat channels subgrid, showing the Chat Widget channel and the Edit button highlighted.](../media/58-chat-widget.png)](../media/58-chat-widget.png#lightbox)

1. In the **Chat channel settings** form, select the **Chat widget** tab and then turn on **Proactive chat**. This setting allows the bot to prompt the user on the website where it's embedded. Select **Copy** to copy the chat widget code and store it for later use, if you haven't done so already. Select **Save and close**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Chat widget tab in Chat channel settings with Proactive chat enabled.](../media/59-proactive-chat.png)](../media/59-proactive-chat.png#lightbox)

1. Return to **Overview** on the left navigation pane. Scroll down to **Workstreams** and then select **Chat**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Overview page with the Chat category highlighted in the Workstreams section.](../media/65-overview-workstreams.png)](../media/65-overview-workstreams.png#lightbox)

1. Select **Chat Workstream** and then select **Edit**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Chat Workstream option in the All workstreams subgrid.](../media/66-chat-workstream.png)](../media/66-chat-workstream.png#lightbox)

1. In the **Chat Workstream** record, select **Edit** for the **Fallback queue**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of selecting Edit for the Fallback queue.](../media/67-edit-fallback-queue.png)](../media/67-edit-fallback-queue.png#lightbox)

1. Select the **Default messaging queue (All users)** from the **Choose existing** dropdown menu.  Select **Save and close**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of selecting the Default messaging queue as the fallback queue.](../media/68-fallback-default.png)](../media/68-fallback-default.png#lightbox)

1. The updated fallback queue displays. Select **+ Add bot** to add the Azure Health Bot for initial routing.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Chat Workstream page and the selection of Add bot.](../media/69-add-bot.png)](../media/69-add-bot.png#lightbox)

1. Select your bot user from the **Name** dropdown menu. Select **Save and close**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of selecting the bot user from the Name dropdown menu.](../media/70-choose-bot.png)](../media/70-choose-bot.png#lightbox)

1. The bot user has been added. Now, you need to edit the ruleset so that the queue properly escalates to a human agent. First, you need a number variable to use with your escalation logic. On the lower-left corner of the **Workstream** page, select **Show advanced settings**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Show advanced settings selection in the lower-left corner of the Workstream page.](../media/71-show-advanced-settings.png)](../media/71-show-advanced-settings.png#lightbox)

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Show advanced settings button.](../media/show-advanced-settings.png)](../media/show-advanced-settings.png#lightbox)

1. Review the advanced settings for the workstream and then select **+ Add context variable**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of selecting the Add context variable option.](../media/72-add-context-variables.png)](../media/72-add-context-variables.png#lightbox)

1. In the **Add context variable** screen, select **+ Add**. Create the new context variable, which you use to determine whether you need to escalate to an agent or not. Enter **EscalateToAgent** as the **Name** and then select **Number** from the **Type** dropdown menu. Select **Create**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of adding context variable details.](../media/73-context-variable.png)

1. The **EscalateToAgent** context variable of the **Number** type should show as added. Close the **Context variables** screen.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Context variables subgrid.](../media/74-variable-added.png)

1. On the workstream record, select **Advanced Settings** to collapse it. Select **Human Agent** under **Ruleset name**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the ruleset name in the Routing rules area.](../media/75-human-agent-ruleset.png)](../media/75-human-agent-ruleset.png#lightbox)

1. Select **Human Agent Rule** and then select **Edit**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Human Agent routing subgrid with Human Agent Rule highighted in the Decision list.](../media/75-human-agent-ruleset-edit.png)](../media/75-human-agent-ruleset-edit.png#lightbox)

1. **Delete** the initial condition in the rule to start with a blank canvas. The logic to follow is having the workstream route the chat channel to a human agent if the **EscalateToHuman** context variable is equal to **1** in any bot conversation.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Edit route to queue rule wizard.](../media/76-delete-default-rule.png)](../media/76-delete-default-rule.png#lightbox)

1. Select **Add > Add related entity** to add a new condition.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of selecting Add related entity from the Add dropdown menu.](../media/77-add-related-entity.png)](../media/77-add-related-entity.png#lightbox)

1. Select **Context item value (Conversation)** from the dropdown menu to have the routing rule check if conversation context values contain specific data.

1. After you select **Context item value (Conversation)**, the following dropdown menu populates with **contains data**, and a sub condition appears. Select the new **EscalateToAgent** context variable, and then set it as **Equals** to **1** in the condition. This setting allows bot conversations to route to a human agent if that variable is ever set to **1**. You view this result in the last exercise in this module. Select **Save and close**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Edit route to queue rule wizard with the condition populated.](../media/80-completed-rule.png)](../media/80-completed-rule.png#lightbox)

The Chat Workstream shows **Human Agent Rule** with the condition that escalates to a human agent when the context variable is set to **1**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Human Agent Rule in the Human Agent ruleset in the Chat Workstream.](../media/81-human-agent-rule.png)](../media/81-human-agent-rule.png#lightbox)

You've now created a chat channel, workstream, queue, context variable, and routing rule that allows customers to begin a conversation with a health bot and escalate to a human agent.
