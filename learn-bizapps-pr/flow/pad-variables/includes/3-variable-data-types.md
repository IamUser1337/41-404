When you create variables in your flows, Power Automate for desktop converts them to a specific type based on their content.

Some of these data types are widely used throughout the application, such as numbers, while others, such as FTP connection, require explicit actions or groups of actions.

The platform supports more than 40 distinct data types and enables you to convert variables between each one of them by just changing the content.  

> [!NOTE]
> To find more information about each data type, please visit the [respective documentation article](/power-automate/ui-flows/desktop/variable-data-types/?azure-portal=true).

For example, you can deploy the **Get clipboard text** action to retrieve your clipboard's current content. The action will store by default the retrieved text in a text variable named **ClipboardText**.

![Screenshot of the Get clipboard text action.](..\media\get-clipboard-text-action.png)

Let's suppose that the clipboard contains only numbers while you are executing this flow, and you want to make calculations with them.

To make calculations, you have to use the **Convert text to number** action to convert the retrieved text to a number. You can either keep the default name for the produced variable or use the existed variable **ClipboardText**.

If you name the produced variable **ClipboardText**, the platform will convert the existing variable to a number variable, and it will store the created number in it.

![Screenshot of the Convert text to number action.](..\media\convert-text-to-number-action.png)

Converting and reusing variables can be a convenient way to reduce the number of variables, but you have to keep track of which content you overwrite. If you are a beginner flow developer, use different variables for each result to avoid unexpected errors.

## Data type properties

Some of the built-in data types have properties that are associated with the value stored in the variables.

Through the properties, you can access information about the variables without the need for additional actions or complicated conversions.

This information can describe the content of the variable or be a part of a multi-component content. For example, you can get the day part of a date or the size of a list with files.

To access the value of a property, you can use the following notation: **%VariableName.PropertyName%**.

For example, if the flow contains a list of files called **Files**, you can get the number of the stored files using the expression: **%Files.Count%**.

![Screenshot of the notation to get the size of a list of files.](..\media\variable-property-example.png)

> [!NOTE]
> To find more information about the available properties, please visit the [respective documentation article](/power-automate/ui-flows/desktop/datatype-properties/?azure-portal=true).
