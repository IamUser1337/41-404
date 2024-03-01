In this exercise, you'll create a flow that calculates how many overtime hours employees have worked. Consider that a typical working day is eight hours.

> [!NOTE]
> Before creating the flow, download the [**Employees.xlsx**](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/raw/master/power-automate-desktop/Employees.zip) file that is required for this exercise. Select **Download** on the right side of the page and extract the downloaded file to your local computer.

1. Launch the Power Automate for desktop console and click on the **+ New flow**.

    ![Screenshot of the Power Automate for desktop.](..\media\build-desktop-flow-initial.png)

1. Name the new flow as **Overtime calculator** and click **Create**.

    ![Screenshot of the Power Automate for desktop Build a flow dialog.](..\media\first-exercise-new-flow.png)

1. Under **Actions** search for **launch**.

    ![Search for launch under actions.](..\media\search-launch-actions.png)

1. Add the **Launch Excel** action to the workspace and configure it to launch the **Employees.xlsx** file.

    ![Screenshot of the Power Automate for desktop Launch Excel action.](..\media\first-exercise-launch-excel-action.png)

1. Under **Actions** search for **get first** and double-click on **Get first free column/row from Excel worksheet**.

    ![Screenshot of the Power Automate for desktop Get first search in actions.](..\media\get-first-action.png)

1. Use the **Get first free column/row from Excel worksheet** action to find the first free row in the file.

    ![Screenshot of the Power Automate for desktop Get first free column/row from Excel worksheet action.](..\media\first-exercise-get-first-free-column-row-from-excel-worksheet-action.png)

1. Under **Actions** search for **loop** and double-click on it.

    ![Screenshot of the Power Automate for desktop Loop action in search results.](..\media\loop-action.png)

1. In **Start from**, manually type in **1**. In **End to**, click on **{X}**, then select **FirstFreeRow**.

    ![Screenshot of the first free row variable.](..\media\excel-first-free-row.png)

1. Update the **End to** formula as shown below. Finally, in **Increment by**, add **1**.

    ![Screenshot of the Power Automate for desktop Loop action.](..\media\first-exercise-loop-action.png)

1. Under **Actions** search for **read from excel**. You can either double-click on **Read from Excel worksheet** or drag-and-drop it between **Loop** and **End**.

    The action is used to read the cell that contains the current employee's total working hours.

    > [!NOTE]
    > In **Variables produced**, double-click on **ExcelData** and change the text to **TotalHours**.

    ![Screenshot of the Power Automate for desktop Read from Excel worksheet action.](..\media\first-exercise-read-from-excel-worksheet-action.png)

1. Under **Actions** search for **run vbs** and drag-and-drop **Run VBScript** below **Read from Excel worksheet**

1. In **VBScript to run** type **result=**, then select the **{X}** and select **TotalHours** and then **Save**.

    ![Screenshot of the Power Automate for desktop Run V B Script action.](..\media\add-total-hours.png)

1. Complete the rest of the script as shown below.

    ![Screenshot of the Power Automate for desktop Run VBScript action.](..\media\first-exercise-run-vbscript-action.png)

1. This is a good time to save the flow you have built so far. 
    
    ![Screenshot of the save flow button.](..\media\save-flow.png)

1. The return value of the **Run VBScript** action is a text value. Use a **Convert text to number** action to convert it to a number.

    ![Screenshot of the Power Automate for desktop Convert text to number action.](..\media\first-exercise-convert-text-to-number-action.png)

1. Use a **Write to Excel worksheet** action to write the numerical value in the current row's third cell.

    ![Screenshot of the Power Automate for desktop Write to Excel worksheet action.](..\media\first-exercise-write-to-excel-worksheet-action.png)

1. Outside the loop, add a **Close Excel** action to save and close the file.

1. Save the flow and then run it to test that every action works as expected.

    ![Screenshot of the Power Automate for desktop final flow and the save and run button.](..\media\first-exercise-final-flow.png)
