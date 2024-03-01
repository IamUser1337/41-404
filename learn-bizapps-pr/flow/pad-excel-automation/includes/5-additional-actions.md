To write data to the first available cell in a given column, use the **Get first free row on column from Excel worksheet** action.

![Screenshot of Get first free row on column Excel worksheet action properties dialog.](..\media\get-first-free-row-on-column-excel-action-properties.png)

The Read and Write actions can use the currently selected cell as a point of reference. Use the **Get selected cell range from Excel worksheet** action for this purpose by providing the indices of the first and last column and row of the selection.

![Screenshot of Get selected cell range Excel worksheet action properties dialog.](..\media\get-selected-cell-range-excel-action-properties.png)

To change the selected cells, use the **Select cells in Excel worksheet** action. Set the **Select** option to **Range of cells** to select cells by specifying the upper-left and bottom-right corner cells.

![Screenshot of Select cells in Excel worksheet action properties dialog.](..\media\select-cells-in-excel-action-properties.png)

Alternatively, set the **Select** option to **Range of cells relative to active cell** to select many cells from the currently selected cell.

To activate a particular cell, use the **Activate cell in Excel worksheet** action. In the **Activate** field, you can either choose to specify a cell by its coordinates (**Absolutely specified cell**) or relative to the currently active cell (**Relatively specified cell**).

![Screenshot of Activate Cell in Excel Worksheet action properties dialog.](..\media\activate-cell-in-excel-action-properties.png)

It's also possible to insert and delete columns and rows by using the appropriate actions; however, you're required to specify a column or row index. In insertion, the row or column will be added before the one that is specified.

![Screenshot of Insert row to Excel worksheet action properties dialog.](..\media\insert-row-to-excel-action-properties.png)

It's now possible to resize the selection of columns or rows in the active worksheet of an Excel instance

![Screenshot of Properties of resize columns rows.](..\media\resize-columns-rows.png)

The **Run Excel macro** action runs a specified macro saved in the workbook. Specify the name of the macro and any parameters separated by semicolons (;). 

![Screenshot of Properties of 'Run Excel macro' action dialog](..\media\run-excel-macro-action-properties.png)

For example, a workbook used by the sales department at Contoso Inc. contains a macro called OrderStatus. The macro requires two arguments, the order number and the username, and returns a customer's order status. To look up order number 778 for the username Rbotas, the **Macro** field in the properties of the action would have to be formatted as follows:

 **OrderStatus;778;Rbotas**

 To use variables rather than providing values directly, format the input as follows:

 **%MacroName%;%OrderNumber%;%UserName%**
