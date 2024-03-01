Although you can handle most of the Power Automate for desktop data types similarly, some data types need distinctive treatment. In this unit, we'll examine these advanced data types that need special handling.

## Lists

If you want to store a high volume of information of the same data type, the best way to achieve it is through lists.

Lists are collections of items that you can reference as a group. Depending on the individual items, you can create lists of text values, numbers, files, etc.

The list data type is the equivalent of a single-dimension array in programming terms, and it functions virtually in the same way.

![Screenshot of a list variable containing folders.](..\media\list-folders.png)

You can create lists through the **Create new list** action and add items to that list through the **Add item to list** action.

![Screenshot of the Create new list action.](..\media\create-new-list-action.png)

You can also create lists through actions that generate lists as output, such as the **Get files in folder** action that returns a files list.

If you want to retrieve a specific item of a list, you can use the following notation: **%VariableName[ItemNumber]%**.

For example, you can rename the first folder of the previously displayed folder list using the following action. Keep in mind that the **ItemNumber** should be 0 for the first item of the list.

![Screenshot of the notation to access the first item of a list.](..\media\access-list-item.png)

> [!NOTE]
> If you want to iterate through the items of a list, a common practice is to deploy a **For each** action.

## Data tables

If you want to store data structured in a tabular form, Power Automate for desktop provides the data tables.

A data table contains rows and columns, and each item stored in it can be retrieved through its unique row and column number. Consider data tables as lists that have other lists as items.

The data tables are the equivalent of a two-dimensional array in programming terms, and it functions virtually in the same way.

![Screenshot of an Excel table containing products and prices.](..\media\excel-table.png)

There is no direct way to create a data table, but you can generate data tables through the **Read from Excel** and the **Execute SQL statement** actions.

If you want to retrieve a specific data table item, you can use the following notation: **%VariableName[RowNumber][ColumnNumber]%**.

For example, you can save the first product's price inside a new variable using the following action. Keep in mind that the **RowNumber** and the **ColumnNumber** should be 0 for the first item.

![Screenshot of the notation to access a table element.](..\media\access-table-element.png)

> [!NOTE]
> If you loop through a data table with a **For each** action, the variable that contains the current iteration's data will be a data row.

## JSON format - custom objects

If you want to use data in JSON format in your flows, Power Automate for desktop provides the custom objects.

Custom objects have a similar structure to JSON, and they are made up of objects and arrays.

The objects are unordered name/value pairs inside curly braces and separated by commas. For example, the following object contains two pairs of names and values **{ "firstName": "John", "lastName": "Michael" }**.

The arrays are ordered collections of values inside brackets and separated by commas. For example, the following array contains four numbers **[1,2,3,4]**.

The combination of these two structures allows you to create ordered lists of name/value pairs.

![Screenshot of a JSON block as parameter in the Convert JSON to custom object action. ](..\media\json-block.png)

You can access individual object values using either the dot (**.**) notation (**Object.PropertyName**) or the bracket (**[]**) notation (**Object["PropertyName"]**).

![Screenshot of the notation to access a JSON element.](..\media\access-custom-object-item.png)

If you want to convert variables between JSON and custom objects data types, you can use the **Convert custom object to JSON** and the **Convert JSON to custom object** actions.
