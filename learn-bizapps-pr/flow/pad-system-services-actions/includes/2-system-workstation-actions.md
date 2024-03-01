In Power Automate for desktop, use flows to launch any of your installed applications with the **Run application** action. In addition to running applications, open any document or file with this action. The action requires the application path and command-line arguments. Optionally, also set a working folder. Set the window state of the application to **Maximized**, **Normal**, **Minimized**, or **Hidden**, and configure the action to wait for the launched application to load or complete.

![Screenshot of the run application action properties.](..\media\run-application-action-properties.png)

Stop any currently running processes in Windows with the **Terminate process** action. Specify the process by name or ID. Either choice requires the input of the corresponding identifier.

![Screenshot of the terminate process action properties.](..\media\terminate-process-action-properties.png)

The **Print document** action requires a file path to print the specified document. The **Set default printer** action requires you to choose from a drop-down list of detected printers and then sets it as the default printer. The **Get default printer** action retrieves the name of the default printer and then stores it in a variable.

![Screenshot of the print document action properties.](..\media\print-document-action-properties.png)

Log the current user off with the **Log off user** action, with an option to **Force log off** if any applications are preventing the operation.

![Screenshot of the log off user action properties.](..\media\log-off-user-action-properties.png)

Shutdown, Restart, Suspend, or Hibernate the computer with the **Shutdown computer** action. The **Force selected action** check box allows the selected operation to persist in case applications are preventing shutdown.

![Screenshot of the shutdown computer action properties.](..\media\shutdown-computer-action-properties.png)

Use the **Show desktop** action to minimize or restore all currently opened windows.

![Screenshot of the show desktop action properties.](..\media\show-desktop-action-properties.png)

Lock the workstation to prevent unauthorized access with the the **Lock workstation** action. This action contains no editable properties.

Play a sound at any point during the flow with the **Play sound** action. Set the action to play a specified system sound or play a .wav file. If you select a .wav file, you will be required to enter the file path.

![Screenshot of the play sound action properties.](..\media\play-sound-action-properties.png)

Permanently delete all contents of the recycle bin using the **Empty recycle bin** action. This action contains no editable properties.

Take a screenshot of the specified screen, all screens, or the foreground window only with the **Take screenshot** action. Copy the image file to the clipboard or save it to a file. To save the screenshot to a file, specify a path and image format.

![Screenshot of the take screenshot action properties.](..\media\take-screenshot-action-properties.png)

Enable, disable, start, or stop the screensaver with the **Control screen saver** action.

![Screenshot of the control screen saver action properties.](..\media\control-screen-saver-action-properties.png)

To ping a remote computer, use the **Ping** action. Specify the remote computer by name or IP, with a configurable timeout. The result and roundtrip time are stored in separate variables.

![Screenshot of the ping action properties.](..\media\ping-action-properties.png)

Set Windows environment variables with the **Set Windows environment variable** action. Specify an environment variable, a value to set, and a type (user or system). The **Get Windows environment variable** action retrieves the value of the specified variable name and store it into a variable. The **Delete Windows environment variable** action deletes the variable with the specified name and type.

![Screenshot of the set environment variable action properties.](..\media\set-environment-variable-action-properties.png)

Set a width, height, bit count, and frequency for the specified monitor with the **Set screen resolution** action. The **Get screen resolution** action retrieves the settings mentioned above for the specified monitor and stores them into separate variables.

![Screenshot of the set screen resolution action properties.](..\media\set-screen-resolution-action-properties.png)
