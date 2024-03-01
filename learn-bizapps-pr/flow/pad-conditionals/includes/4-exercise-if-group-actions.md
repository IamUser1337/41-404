In this exercise, you will apply some of the **If** actions available, in order to identify the capabilities they offer.

1. Use a **Get Special Folder** action to retrieve the path to the desktop.

1. Check whether a folder named **Records** exists in the desktop. To do this, use the **If Folder Exists** action, and configure its input as follows:

    ![Screenshot of the If folder exists dialog.](..\media\if-records-folder-exists.png)

1. Inside the **If** block, add an **If File Exists** action to check if the **Expenses** Excel file exists inside the **Records** folder. Configure it as follows:

    ![Screenshot of the If file exists dialog.](..\media\if-expenses-file-exists.png)

1. This will only run if the Folder exists. By this stage, your flow should look like this:

    ![Screenshot of the initial flow structure.](..\media\initial-flow-structure.png)

1. If the file exists, move it to the desktop folder using the **Move Files** action. Otherwise, the user should be notified; add an **Else** action inside the second if block, and a **Display Message** action to inform the user that the file has already been moved.

1. Finally, in case the folder itself does not exist, add an **Else** action inside the first **If** block, and a second **Display Message** action to inform the user that the **Records** folder does not exist:

    ![Screenshot of the Outside else display message.](..\media\outside-else-display-message.png)

1. We suggest that you run the flow, trying different scenarios.
