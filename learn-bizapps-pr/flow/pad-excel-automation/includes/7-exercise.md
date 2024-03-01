This exercise shows how you can use certain actions to organize data in an Excel spreadsheet.

## Tasks

In this exercise, you will:

- Attach to an open Excel file and add a header to each column.
- Switch the positions of two columns.
- Copy and paste cells.
- Delete a blank column.
- Run the flow to verify successful completion.

### Attach to an Excel file and add headers

To begin, download [**Customers.xlsx**](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/raw/master/power-automate-desktop/Customers.zip). Select **Download** on the right. Extract the Excel file to your local computer. Then, follow these steps to attach to this running Excel file:

1. Create a new flow and then add the **Launch Excel** action.

1. Specify the name of the file in the action properties (**Customers.xlsx**).

   ![Screenshot of Attach to running Excel properties dialog.](..\media\attach-to-running-excel-exercise.png)

The Excel document contains a list of customers. Each customer has a first name, a last name, an address, a state, and a city.

1. Insert a row with headers by using the **Insert row to Excel worksheet** action, specifying the **Row index**. To add a row at the top of the worksheet, set the **Row index** property to **1**.

   ![Screenshot of Insert row to Excel worksheet properties dialog.](..\media\insert-row-to-excel-exercise.png)

1. Add five **Write to Excel worksheet** actions, one for each column (or header). In the first of these actions, set **Value to write** to **First Name**, and then set the **Column** property to **A**.

    ![Screenshot of Write to Excel worksheet properties dialog.](..\media\write-to-excel-exercise.png)

    The rest of the **Write to Excel worksheet** actions should be configured as follows:

    - **Last Name** — Column B
    - **Age** — Column C
    - **State** — Column D
    - **City** — Column E

### Switch positions of two columns

Next, to switch the positions of the last two columns so that **State** appears after **City**, follow these steps:

1. Select the **Get first free row on column from Excel worksheet** action, which will retrieve the index of the first available row in the column of your choice.

2. Because you will be moving the **State** column, select column **D**.

    ![Screenshot of Get first free row on column from Excel worksheet properties dialog.](..\media\get-first-free-row-on-column-excel-exercise.png)

### Copy and paste cells

To copy the cells, follow these steps:

1. Select the **Copy cells from Excel worksheet** action.

2. In the **Copy mode** options, select **Values from a range of cells**.

3. Set the **Start column** to **D** and **Start row** to **1**.

4. Set the **End column** to **D** and then set **End row** to **%FirstFreeRowOnColumn-1%** so that the entire column is dynamically selected without having to calculate its length.

    ![Screenshot of Copy cells from Excel worksheet properties dialog.](..\media\copy-cells-from-excel-exercise.png)

To paste cells, follow these steps:

1. Select the **Paste cells to Excel worksheet** action.

2. Set the **Column** property to **F** and the **Row** property to **1**. This setting will paste the cells in the clipboard into the specified cell.

    ![Screenshot of Paste cells to Excel worksheet properties dialog.](..\media\paste-cells-to-excel-exercise.png)

### Delete a blank column

To delete the blank column, select the **Delete column from Excel worksheet** action and then set the **Delete column** property to **D**.
  
![Screenshot of Delete column from Excel worksheet properties dialog.](..\media\delete-column-from-excel-exercise.png)

Save and quit the file by adding the **Close Excel** action and then selecting to save the document before closing.
  
![Screenshot of Close Excel properties dialog.](..\media\close-excel-exercise.png)

The completed flow should look like the following screenshot.

![Screenshot of the completed Excel exercise workspace.](..\media\excel-exercise-workspace.png)

## Run the flow

Run the flow to see that a new row has been inserted, the headers have been written, and the last two columns have switched positions.
