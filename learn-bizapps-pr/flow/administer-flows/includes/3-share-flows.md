In the Power Automate mobile app, you can share button flows with other users
or groups in your organization. The users or groups with whom you share a button
can then run it the same way they run their own buttons.

You can also share a link to buttons that another person shared with you.

You can stop sharing your buttons at any time.

The screenshots in this unit were taken on a Apple iOS device. If you're using
an Android or Windows device, what you see might differ, but the functionality
is the same.

## Prerequisites

To share buttons, you need:

* An account that has access to [Power Automate](https://flow.microsoft.com/?azure-portal=true
).
* A flow to share.
* A mobile device that has the Power Automate mobile app for [Android](https://aka.ms/flowmobiledocsandroid/?azure-portal=true
), [Apple iOS](https://aka.ms/flowmobiledocsios/?azure-portal=true
), or [Windows Phone](https://aka.ms/flowmobilewindows/?azure-portal=true
).
* A person or group in your organization with whom to share your button.

## Share a button

You share a button by using the **Buttons** tab of the Power Automate mobile app.

1. Start the Power Automate mobile app.

1. On the **Buttons** tab, select the three dots next to the button that you want to share.

    ![Screenshot of the Buttons tab with the ellipsis button highlighted next to the Send myself a reminder in 10 minutes button.](../media/share-button-flows-buttons-tab.png)

1. On the pop up, select **Invite others**.

    ![Screenshot of the Buttons tab with the button menu showing Invite others and Share button links options. Invite others is highlighted.](../media/share-button-flows-button-users.png)

1. On the following page you can manage users with whom you have already shared the flow. For this exercise, select **Invite others** again to continue with sharing.

1. Search for and select the person or group that you want to share the button with.

1. Select **Send**.

1. On the page that states that the button sharing action was successful, select **Done**.

## Require users to use their own connections

When you share a button with other people, you can either let them use all the connections that the button uses or require that they use their own connections. Follow these steps to require the people with whom you share your button to use their own connections.

> [!NOTE]
> If you let other people use your connections, they can't access the credentials in your connection. They also can't reuse those connections in any other flow.

1. On the page that appears immediately after you share a button, select **Manage connections**.

1. Select **Edit** for the connection that you want to manage.

1. Select **Provided by user** or your email address to specify whose connections must be used in the shared button.

    ![Screenshot of Users and connections Choose which connection to use for "Notifications" with Provided by user selected.](../media/share-button-select-connection-provided-by-user.png)

    You can view or change your selection at any time.

    1. On the **Flows** tab, select the flow that you shared.
    1. On the **Users and connections** page, on the **Connections** tab, select **Edit** for the button that you want to manage.

## Stop sharing a button

You can stop sharing a button by following these steps.

1. On the **Buttons** tab, select the three dots next to the button that you want to stop sharing.

    ![Screenshot of the Buttons tab with the ellipsis button highlighted next to the Send myself a reminder in 10 minutes button to stop sharing.](../media/share-button-flows-buttons-tab.png)

1. On the pop up, select **Invite others**.

    ![Screenshot of the Buttons tab with the button menu showing Invite others and Share button links options. Invite others is highlighted again.](../media/share-button-flows-button-users.png)

1. On the following page you can manage users with whom you have already shared the flow. On this page, select the user which you wish to remove.

1. On the user's page, select **Remove user**.

    ![Screenshot of John Doe's page with Remove user highlighted.](../media/share-button-flows-remove-user.png)

1. Wait for the removal action to be finished. The list on the **Button users** page is refreshed, and the user or group that you removed is no longer listed.

## Monitor the run history

You can view the whole run history, even for runs started by a person that a button is shared with.

1. Start the Power Automate mobile app.
1. Select the **Activity** tab to view the run history.

## Use shared buttons

Before you can run a button that someone has shared with you, you must add it to your **Buttons** tab from the **Add buttons** page.

1. On the **Buttons** tab, select **Get more** (or the **New buttons are available** banner if it appears).

1. Select the button to use.

    The button is immediately added to the **Buttons** tab. You can then run the button from the **Buttons** tab, just like any other button that's listed there.

## Re-share a button

You can share a link to a button that has been shared with you.

1. On the **Buttons** tab, select the three dots next to the button that you want to share.

    ![Screenshot of the Buttons tab with the ellipsis button highlighted next to the Send myself a reminder in 10 minutes button to re-share.](../media/share-button-flows-buttons-tab.png)

1. Select **Share button link**.

1. Select the app that you want to use to share the button.

1. Follow the steps for sending a button to a person that you want to share it with.

## Stop using a shared button

If you no longer want to use a button that was shared with you, you can remove it.

1. On the **Buttons** tab, select the three dots next to the button that you no longer want to use.

    ![Screenshot of the Buttons tab with the ellipsis button highlighted next to the Send myself a reminder in 10 minutes button to stop using.](../media/share-button-flows-buttons-tab.png)

1. Select **Remove**.

> [!NOTE]
> After you remove a shared button, you can add it back by selecting **Get more** on the **Buttons** tab.
