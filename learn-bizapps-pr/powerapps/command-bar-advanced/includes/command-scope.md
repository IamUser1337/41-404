When new commands are added to a command bar using the command bar designer, the command is scoped to that specific command bar location in a specific app for a specific table. By manually editing the command definition, you can broaden the command scope. You can configure commands with the following scope:

-   **App** - App is the default configuration, and the command is for a specific command bar location, app, and table.

-   **Table** - Table is a broader scope of the command, and the command is visible anytime an app is in the environment using the same table and command bar (for example, Main form).

-   **Global** - Global is the broadest scope of the command, and the command is visible in the same command bar location (example, main form) for all tables in all apps in the environment.

Having your command be broader scope can increase the reusability of the command. This expanded scope can also help with usability because the user has consistent access to the same command. Currently, commands that use Power Fx for the Visibility or OnSelect action can only be App scope.

The command bar designer doesn't allow configuring a command for a scope other than App. To configure Table or Global scope, it's necessary to manually edit the command definition file. In the following video, you'll learn how to change a command's scope.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RW11Zlx]
