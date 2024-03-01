In attended automation, the interaction between users and workstations is essential. Message boxes provide a direct means for this communication to take place.

In this exercise, you'll develop an attended flow that reads orders from Excel worksheets and prompts users to select a discount for high-value orders.

To begin, download [**Orders.zip**](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/raw/master/power-automate-desktop/Orders.zip). Select **Download** on the right and extract the Excel file to your local computer.

1. Start by prompting the user to select an Excel file. Use the **Display select file dialog** action and configure the **File filter** field to allow only **xlsx** files.

   ![Screenshot of the Display select file dialog action.](..\media\display-select-file-dialog-properties-exercise.png)

1. Before reading any data from the selected file, you have to launch it using the **Launch Excel** action.

   ![Screenshot of the Launch Excel action.](..\media\launch-excel-action-exercise.png)

1. To read the data from the Excel file, deploy the **Read from Excel worksheet** action and select **All available values from worksheet** in the **Retrieve** field.

   ![Screenshot of the Read from Excel worksheet action.](..\media\read-from-excel-worksheet-properties-exercise.png)

1. Deploy the **Get first free column/row from Excel worksheet** action to retrieve the first free column and row in the Excel worksheet.

   ![Screenshot of the Get first free column row from Excel worksheet action.](..\media\get-first-free-column-row-exercise.png)

1. Use the **Write to Excel worksheet** action to add a **Discount** header in the first free column of the Excel file.

   ![Screenshot of the Write to Excel worksheet action that writes the Discount header.](..\media\write-excel-worksheet-exercise.png)

1. Before handling each Excel row independently, create a new variable named **Counter** and initialize it to **2**. This variable will indicate the number of the row you're handling in each iteration. 

   ![Screenshot of the Set variable action.](..\media\set-variable-action-exercise.png)

1. Add a **For each** loop to iterate through the retrieved data.

   ![Screenshot of the For each properties dialog.](..\media\for-each-properties-exercise.png)

1. To check the value of the **Gross** column (column G), convert it into a number, and then add an **If** action to check whether it exceeds 100,000.

   ![Screenshot of the Convert text to number action.](..\media\convert-text-to-number-properties-exercise.png)

   ![Screenshot of the exercise workspace with the if block added.](..\media\exercise-workspace.png)

1. If the value exceeds 100,000, the user should decide whether to add a discount. Deploy the **Display message** action to provide the necessary information to the user, and prompt them to choose **Yes** or **No**.

   ![Screenshot of the Display message action.](..\media\display-message-properties-exercise.png)

1. Add a second **If** action to check which button was pressed in the previous step.

   ![Screenshot of the If action.](..\media\if-properties-exercise.png)

1. If the user selects **Yes**, a window will prompt them to enter the discount amount; use the **Display input dialog** action to achieve this functionality.

   ![Screenshot of the Display input dialog action.](..\media\display-input-dialog-properties-exercise.png)

1. Write the selected discount amount into the **Discount** column of the Excel file.

    ![Screenshot of the Write to Excel worksheet action.](..\media\write-to-excel-worksheet-properties-exercise.png)

1. Before exiting the previously created **For each** loop, use the **Increase variable** action to increase the **Counter** variable by one.

    ![Screenshot of the Increase variable action.](..\media\increase-variable-action-exercise.png)

1. Finally, run the flow. When prompted, select the **Orders.xlsx** file.

    ![Screenshot of the completed exercise workspace.](..\media\final-exercise-workspace.png)
