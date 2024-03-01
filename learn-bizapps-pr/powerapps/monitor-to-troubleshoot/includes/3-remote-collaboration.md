Monitor supports three options for collaborating with others:

-   **Download/Upload** - These options allow you to collaborate by saving a Monitor
    session to a local file that you can reload later or share with
    someone else to collaborate. For example, you can save the session
    locally and then upload and attach it to a work item that you could
    assign to another developer. Then, the assigned developer can reload
    the session into Monitor on their own schedule to view the events
    that occurred.

-   **Invite** - With this option, you can collaborate in real time with
    another person to watch the Monitor event log as you run the
    application from Power Apps Studio. Because the app is run from
    Power Apps Studio, this option is intended for use during development of
    the app, not for supporting deployed apps. For example, this option
    might be helpful in a scenario where another colleague on your team
    created a custom connector and you're having problems using it. You
    could invite that colleague to view your application's use of the
    connector and monitor it by using the **Invite** feature.

-   **Connect user** - This option allows you to use Monitor to connect to a
    remote user who is running a published canvas app from Power Apps. For example,
    a user might experience a problem that you are unable to
    reproduce in your development environment. By using the **Connect user** feature, you
    can invite them to run the application while you watch the event log
    in the Monitor tool.

Regardless of which option that you choose, collaboration can accelerate the
resolution of app problems. In these scenarios, users whom you
collaborate with will have access to the events and the data that was
used in the app. The rest of this module will describe other
factors to consider when you're using each option.

## Use Download/Upload

Monitor includes a built-in feature that allows you to download the current session's
events to a local file. You can reload the downloaded file into any
Monitor session by using the **Upload** feature.
This process won't have a negative effect on the contents of the current session's file; the feature
only allows you to reload the events later. You can initiate these actions from any Monitor session by using the command bar buttons.

:::image type="content" source="../media/download-monitor.png" alt-text="![Screenshot showing the Upload and Download command bar buttons.]":::

The simplest use of the downloaded file is to reload it later into
your own Monitor session. For collaboration, you can share the file
(email, OneDrive, GitHub Issues, or Microsoft Azure DevOps work items, and so on) with
anyone who has Monitor access, and they can reload the file, even if they
don't have edit access to the app that was monitored. This feature allows you
to consult with a colleague that might be more familiar with some
interactions of specific connectors.

Additionally, you can use this option to save a baseline of an app that you can
use for future comparison. For example, if your queries were slow,
it would be beneficial if you could identify those queries from
the previous time when you were testing.

Using the download and upload process is best for collaborating when you
don't need real-time collaboration. It can work well where the people who are
involved are in different time zones.

## Use the Invite feature

By selecting the **Invite** feature, you can invite another user in your
organization to access Monitor and view the events that you are generating by
previewing the app in Power Apps Studio. You can initiate the invite by
selecting **Invite** from the command bar.
When you provide the user information, the invite link will generate.

:::image type="content" source="../media/invite-user.png" alt-text="![Screenshot showing the Invite people to this session link.]":::

Make sure that you copy the link and provide it to the user so that they can launch
Monitor and listen to your session. The link is only good for 60 minutes.
If you need more time, remove and then reinvite the user. If you
invite the wrong user, you can remove the invite; the person will not be notified
of the invite.

The following diagram illustrates the process of using the **Invite** feature, where you are represented as User A and the
other user is User B.

:::image type="content" source="../media/invite-process.png" alt-text="![Screenshot showing what happens when you invite a user.]":::

Each user receives their own copy of the events, meaning that you can
browse, view, and inspect the app events independently, without
interfering with each other or handing control back and forth to
identify the problem. For example, if you select **Clear data**, it will only
clear your event log, not the other users' event logs.

Keep in mind that, while the other user can view the Monitor events, they can't
observe what you're doing in the application. Often, it can be
helpful to also have a screen-sharing session where the user who is
watching the Monitor events can also watch what you're doing in the
app.

Because the user who has been invited to monitor your app session doesn't
run the app, you are not required to share the app, or specific app permissions, with them.

## Use the Connect user feature

The **Connect user** feature allows you to select a published app that is
enabled for debug and to invite a user to run the app while you use Monitor
to listen to the events that it generates.

:::image type="content" source="../media/connect-user.png" alt-text="![Screenshot showing what happens when you connect a user and they play the app.]":::

To enable the app, turn on the **Debug published app** setting.
After you have changed this setting, save and republish the app.

:::image type="content" source="../media/debug-published.png" alt-text="![Screenshot showing the Debug published app option.]":::

Because the **Debug published app** option adds debug information to the application, it can slow
the implementation; therefore, you should only enable the option when necessary.

To use the **Connect user** feature, launch Monitor from the app
list rather than from Power Apps Studio.

:::image type="content" source="../media/launch-monitor.png" alt-text="![Screenshot showing Monitor being launched from the app list.]":::

When Monitor launches, the **Connect user** button will be visible
in the command bar.

:::image type="content" source="../media/connect-user-button.png" alt-text="![Screenshot showing the Connect user button from the command bar in the Monitor app.]":::

Similar to the **Invite** feature, you will provide the user information, and then a link will be
generated so that you can share with the user whom you want to run the app.

However, unlike the **Invite** feature, the user will run the application, so you will need to share the app
and provide the necessary permissions for them to use it.

When the user selects the link to run the app, your Monitor session will show
the events that are generated by the user who is running the app. In many cases, you might
find it helpful to have a screen-sharing session so that you can view what
they're doing in the app as you view the events in Monitor.

The collaboration features of Monitor allow you to work with others to
troubleshoot problems in apps, even when you aren't located in the same
place.
