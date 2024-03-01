Microsoft Power Automate provides two options for you to share flows with your colleagues. You can add your colleagues as either co-owners or run-only users. Co-owners have full edit permissions for the flow, whereas run-only users can only run the flow.

You can add users as individuals, security groups, or Office 365 groups. The following sections explain how to share your button flows.

## Share button flows as a co-owner

To share your app with a co-owner, follow these steps:

1. Using a computer browser, go to your flow\'s **Share** option by selecting the ellipsis (**\...**) next to your flow in the **My flows** list. You can also go to your flow and select the **Share** button on the upper portion of the button flow.

    ![Screenshot of the Share option flows list.](../media/share-option-flows-list.jpg)

    ![Screenshot of the Power Automate Share option flow.](../media/share-option-flow.jpg)

1. Enter either the user or the group name and then select it.

    ![Screenshot of the Set Out of Office dialog with add a user or group as owner option highlighted.](../media/add-user-group.jpg)

1. You will receive a message stating that owners of the flow will have full access to all connections in the flow and the content within the connected accounts. Select **OK**.

1. Select the left arrow next to the flow name.

You have now successfully shared your button flow by adding a co-owner.

## Share button flows as a run-only user

Run-only users provides an added bonus feature where you can allow users to provide their own connection. This means that when the flow runs, the context of the user running the flow is passed instead of using the connection configured in the flow. It is important to note that users that use the default connection will not have access to the connection outside the flow.

To add run-only users, follow these steps:

1. Select **Edit** in the **Run only users** section.

    ![Screenshot of the Set Out of Office dialog with the edit button in the run only users section highlighted.](../media/add-run-only-users.jpg)

1. Select either the username or the group name and then select which data connector that the person should use. The person can either use the connection that you created or a connector that they provided themselves. Select **Save**.

    ![Screenshot of the Manage run-only permissions dialog with user connector access.](../media/run-user-connector-access.jpg)

## Share button flows directly from your mobile app

To invite users to run your button flow directly from your mobile app, follow these steps:

1.  Sign in to your Power Automate mobile app and then select the **Buttons** icon on the lower horizontal menu of the app.

1.  Select the ellipsis (...) next to the flow button and then select **Invite Others**. Search for the name of the person or group in the **Search people or groups** field.

1.  Select the user or group name and then select **Send** on the upper right of the screen.

1.  Select **Done** on the upper right of the screen.

    You should see a list of users and groups with whom the button flow has been shared.

## Verify that the user can access the shared button flow

To verify that the user can access the shared button flow, follow these steps:

1.  Have the user that you shared the button with sign in to the Power Automate app on their smartphone. Select the **Button** icon on the lower horizontal menu.

1. Select **New buttons are available**.

    ![Mobile screenshot of the new buttons available.](../media/new-buttons-available.jpg)

1. The user should see the new button that was shared. Select the flow button name.

1. Select the **Add to Buttons** tab button on the lower portion of the screen.

    ![Mobile screenshot of the add buttons tab.](../media/add-buttons-tab.jpg)

1. Select the arrow on the upper left of the screen.

You will now see the new button in your **Buttons** menu.
