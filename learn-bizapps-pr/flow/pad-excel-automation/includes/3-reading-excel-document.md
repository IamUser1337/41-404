Reading an Excel document retrieves the data from the document, allowing it to be processed and modified in flows.

Read and extract data from an Excel document with the **Read from Excel worksheet** action.

Select the Excel instance and specify the range of data to read. Set the **Retrieve** option to **The value of a single cell** to retrieve the contents of a single cell, and then specify the cell location with the **Column** and **Row** properties.

![Screenshot of Read from Excel worksheet action properties dialog.](..\media\read-from-excel-action-properties.png)

To extract a table of data, set **Retrieve** to the **Values from a range of cells** option. Define the table by the coordinates in the **Start column/row** and **End column/row** properties. Specify the column by its letter or corresponding number. For example, you can enter **column E, row 8** or **column 5, row 8** for cell E8. This output will be of a **datatable** type variable.

Variables store cell contents based on their type. For example, a date is stored as a **datetime** variable. To store all data as text, select the **Get cell contents as text** option. When selecting to read values from a range of cells, select **First line of range contains column names** to ignore the first row. To ignore the type of data in the cell and retrieve the contents as text, select **Get cell contents as text**. Change these properties in the **Advanced** section.

![Screenshot of Read from Excel worksheet properties advanced section.](..\media\read-from-excel-properties-advanced-tab.png)

Alternatively, select cells in the document to which the instance is assigned, and use the **Values from selection** option to retrieve the values of the currently selected cells. To retrieve all data from an Excel worksheet, select **All available values from worksheet** in the **Retrieve** field.

![Screenshot of the Retrieve field in the Read from Excel worksheet action.](..\media\read-from-excel-action-properties-all-values.png)
