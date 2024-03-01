When a flow runs, a user may encounter unforeseen circumstances, resulting in it stopping due to an error. To avoid errors, users can configure exception handling rules, so that the flow can recover and continue running.

In the flow designer, exception handling may be applied to individual actions.

## Exception handling

Exceptions may occur from virtually any action. For this reason, most actions’ properties contain an **On error** button.

In our example, the flow is executed in company devices where the Excel file can be in either the **C:** or the **D:** drive. The rest of the path location is the same. For this situation  we could configure the **Launch Excel** action so that, if it fails to open the file from the **C:**, it will attempt to open it from the **D:** path.

To achieve this, we'll double-click on the action to edit it and select the **On error** button:

![Screenshot of the Launch Excel action properties dialog.](..\media\launch-excel-action-properties-2.png)

You can toggle on the **Retry** option and initially leave the default settings as is. This will retry the action one more time after an interval of 2 seconds. You have the option to adjust these settings later on.

![Screenshot of the Launch Excel action properties exception handling retry action.](..\media\launch-excel-action-properties-exception-handling-retry.png)

Then select the **Continue flow run** option.

![Screenshot of the Launch Excel action properties exception handling.](..\media\launch-excel-action-properties-exception-handling.png)

You have a few options to handle the exception. You can either go to the next action, repeat the existing one or go to a label.

![Screenshot of the exception handling.](..\media\continue-flow-run.png)

The selected options will take effect when this action encounters an exception. To open a file in a different path, we'll have to create a new subflow that does exactly that.  The **Advanced** section will allow you to create rules, which allow you to run **Subflows**.

![Screenshot of the alternative path subflow.](..\media\advanced-flow-errors-settings.png)

![Screenshot of the advanced flow settings.](..\media\alternative-path-subflow.png)

Then configure the previous action’s exception handling accordingly, by pressing **New rule** and selecting **Run subflow**:

![Screenshot of the Launch Excel action properties exception handling with alternative path added.](..\media\launch-excel-action-properties-exception-handling-continued.png)

Configured as above, if the Excel file can't be opened in its usual path, the Alternative Path subflow will run, opening the file in its alternative path, then the flow will resume running.
