In this exercise, you'll create a flow that copies a selected folder and then adds information about the created backup in a Microsoft Excel file.

To create the flow:

1. Launch Power Automate for desktop and then select the **New flow** button in the console.

    ![Screenshot of the New flow button in the console.](..\media\exercise-new-flow-button.png)

1. Choose a name for your flow and then select the **Create** button. For this example, the flow is named **Backup flow**.

    ![Screenshot of the Build a flow dialog box.](..\media\exercise-build-a-flow-dialog.png)

1. When the flow designer is launched, add a **Display select folder dialog** action to prompt users to select a folder.

    ![Screenshot of the Display select folder dialog action dialog.](..\media\exercise-display-select-folder-dialog-action.png)

1. Use a **Copy folder** action to copy the selected folder in your documents folder.

    >[!IMPORTANT]
    > Make sure the destination folder already exists so that the flow can copy the files.

    ![Screenshot of the Copy folder action dialog.](..\media\exercise-copy-folder-action.png)

1. Deploy a **Launch Excel** action to open the Excel file that contains the logs about your backup activity. 

    1. If this file doesn't already exist, create a blank Excel spreadsheet named **Logs.xlsx** in the **Desktop** folder so that the automation will be able to open it as an existing file. 

    ![Screenshot of the Launch Excel action dialog.](..\media\exercise-launch-excel-action.png)

1. To find the first available row in the Excel file, use the **Get first free column/row from Excel worksheet** action.

    ![Screenshot of the Get first free column/row from Excel worksheet action dialog.](..\media\exercise-get-first-free-column-row-from-excel-worksheet-action.png)

1. To get a timestamp of the current time for the logs, use the **Get current date and time** action.

    ![Screenshot of the Get current date and time action dialog.](..\media\exercise-get-current-date-and-time-action.png)

1. Deploy two **Write to Excel worksheet** actions to add log information in the Excel file. 

    1. Use the first **Write to Excel worksheet** action to write the copied folder's path in the first column of the first available row.

        ![The Write to Excel worksheet action writing the folder's path.](..\media\exercise-write-to-excel-worksheet-action.png)
    
    1. Use the second deployed action to add a timestamp in the second column of the first available row.

        ![Screenshot of the Write to Excel worksheet action writing the timestamp.](..\media\exercise-write-to-excel-worksheet-second-action.png)

1. Use a **Close Excel** action to save and close the Excel file.

    ![Screenshot of the Close Excel action dialog.](..\media\exercise-close-excel-action.png)

1. To test that the flow runs as expected, select the **Run** button, pick a folder, and then check that the log file has been updated.

    ![Screenshot of the final flow and the run button.](..\media\exercise-final-flow.png)

1. If the flow works as expected, save it and then close the flow designer.
