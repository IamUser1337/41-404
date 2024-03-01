In this unit, you'll develop a flow that converts dates in the dd/MM/yyyy format, commonly used in Europe, to the American format (MM/dd/yyyy). The flow will prompt users to enter a date and it will display the converted date in a message box. 

> [!NOTE]
> Το make the flow work with date formats used in other regions, replace the presented date formats with the ones you want to use.

To create the flow:

1. Launch Power Automate for desktop and select the **New flow** button in the console.

    ![Screenshot of the New flow button in the console.](..\media\console-new-flow.png)

1. Populate a name for the flow and then select the **Create** button. In this example, the flow is named **Date conversion**.

    ![Screenshot of the Build a flow dialog box.](..\media\console-build-new-flow.png)

1. When the flow designer is launched, use the **actions** pane to search for and select the **Display input dialog** action. 
    
    ![Screenshot of search in Actions pane.](..\media\actions-search.png)

    > [!NOTE]
    > If the searching term matches a module name, the results display the module expanded with all its actions available. Searching also returns partial matches, but requires at least two provided characters.

	In addition, you can either double-click on this action or you can drag and drop from the actions to the main pane.

	![Screenshot of drag and drop.](..\media\drag-and-drop.png)

1. Set the action to prompt users to enter a date in the European format.

    ![Screenshot of the Display input dialog action.](..\media\display-input-dialog-action.png)

1. Deploy a **Convert text to datetime** action to convert the entered text to a datetime variable. The text represents the European date format, so configure the appropriate custom format in the action's properties.

    ![Screenshot of the Convert text to datetime action.](..\media\convert-text-to-datetime-action.png)

1. To convert the datetime variable to the American date format, use the **Convert datetime to text** action with the appropriate custom format in its properties.

    ![Screenshot of the Convert datetime to text action.](..\media\convert-datetime-to-text-action.png)

1. Use the **Display message** action to display the converted date in a message box.

    ![Screenshot of the Display message action.](..\media\display-message-action.png)

1. To test the flow, select the **Run** button, populate a date in the European format, and verify that the flow displays the appropriate American date format. To check how every single action is implemented, run the flow step by step using the **Run next action** button.

    ![Screenshot of the Run and Run next action buttons in the flow designer.](..\media\run-next-action-icon.png)

1. If the flow runs as expected, select **Save** and then close the flow designer.

    ![Screenshot of the Save button in the flow designer.](..\media\save-icon.png)

1. Now, you can also run your flow manually through the **Run** button in the console. If you want to stop running the flow, select the **Stop** button.

    ![Screenshot of the run button in the console.](..\media\run-date-conversion-flow.png)
