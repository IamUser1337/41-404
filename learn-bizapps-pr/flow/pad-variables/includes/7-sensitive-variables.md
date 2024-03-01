When running desktop flows through the flow designer, you can review the values of all the deployed variables. This functionality makes debugging more straightforward, as you can check the state of the desktop flow at any given moment.

However, some scenarios handle sensitive information that mustn't be visible for security reasons. Power Automate allows you to hide the content of a variable by marking it as sensitive.

The values of sensitive variables aren't visible in the variables pane of the flow designer. Additionally, the values aren't logged in the Power Automate portal when the flow runs from the console or a cloud flow.

![Screenshot of a sensitive variables in the workspace.](..\media\sensitive-variable-example.png)

Sensitive variables can be manipulated, referenced, processed, and used in every action without any limitation, like every other variable. 

To set a variable as sensitive, right-click on its name in the variables pane and select **Mark as sensitive**. To stop a variable from being sensitive, right-click on it and select **Mark as not sensitive**. 

![Screenshot of the Mark as sensitive option in the flow designer.](..\media\mark-sensitive-variable-option.png)

Apart from the context menus, you can use the dedicated icon next to each variable name to mark it as sensitive or not sensitive.

You can mark any variable as sensitive independently of its type. When a structured datatype, such as a list, a datarow or a datatable, is marked as sensitive, the variable is marked as a whole.

![Screenshot of the Mark as sensitive icon in the flow designer.](..\media\mark-sensitive-variable-option-icon.png)