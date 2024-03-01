In this exercise, you will create a flow that prompts users to enter information about new clients and then register them into an Excel file.

1. Launch Power Automate for desktop and create a new flow named **Client registration**.

    ![Screenshot of the Build a flow dialog.](..\media\exercise-create-flow.png)

1. Deploy a **Display input dialog** action and populate the **Input dialog message** field with a message asking for the client's name.

    ![Screenshot of the Display input dialog action.](..\media\exercise-input-dialog-message-action.png)

1. Rename the **UserInput** produced variable to a more descriptive name, such as **NameInput**.

    ![Screenshot of the renamed produced variable in the Display input dialog action.](..\media\exercise-input-dialog-message-action-produced-variable.png)

1. Repeat the last two steps 3 more times for the last name, the phone number, and the country code, respectively.

    ![Screenshot of all the Display input dialog actions.](..\media\exercise-all-input-dialog-message-actions.png)

1. Add a **Set variable** action in the workspace to join the name and the last name into a new variable called **FullName**.

    ![Screenshot of the Set variable action containing the full name.](..\media\exercise-set-variable-action-full-name.png)

1. Repeat the fifth step to join the country code and the phone number into a variable called **FullPhoneNumber**.

    ![Screenshot of the Set variable action containing the full phone number.](..\media\exercise-set-variable-action-full-phone-number.png)

    Because both variables have been created through a **Display input dialog** action, they are texts and not numbers. If the variables were numbers, the action above would have performed addition and not string concatenation.

1. Add a **Launch Excel** action to open the Excel file containing the clients' information.

    ![Screenshot of the Launch Excel action properties dialog.](..\media\exercise-launch-excel-action.png)

    The file must contain two columns, one for the clients' full name and one for the phone number.

    ![Screenshot of the structure of the Excel file.](..\media\exercise-excel-file.png)

1. Use the created Excel instance as an input for a **Get first free column/row from Excel worksheet** action.

    ![Screenshot of the Get first free column/row from Excel worksheet action.](..\media\exercise-get-first-free-column-row-from-excel-worksheet-action.png)

1. Deploy a **Write to Excel worksheet** action and populate the fields with the following values:

    - The **Excel instance** field with the respective Excel instance variable.
    - The **Value to write** field with the **FullName** variable.
    - The **Column** field with the value **1**.
    - The **Row** field with the **FirstFreeRow** variable.

    ![Screenshot of the first Write to Excel worksheet action.](..\media\exercise-first-write-to-excel-worksheet-action.png)

1. Repeat the previous step, populating the **Value to write** field with the **FullPhoneNumber** variable and the **Column** field with the value **2**.

    ![Screenshot of the second Write to Excel worksheet action.](..\media\exercise-second-write-to-excel-worksheet-action.png)

1. Lastly, add a **Close Excel** action to save and close the launched Excel worksheet.

    ![Screenshot of the Close Excel action dialog.](..\media\exercise-close-excel-action.png)

1. Now, the flow must be the same as the image below. To check that runs as expected, select the **Run** button.

    ![Screenshot of the final flow and the run button.](..\media\exercise-final-flow.png)
