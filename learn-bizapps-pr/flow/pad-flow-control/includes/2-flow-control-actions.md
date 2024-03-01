By default, a flow moves from one action to the next in the order that these actions appear in the workspace.

Certain actions, such as the **Go to** action or the **Exit subflow** action, interrupt the default running order of the flow and direct it to another point in the same subflow or another subflow.

Labels are used to create points of reference for the **Go to** action to direct the flow to.

The **Run subflow** action interrupts the subflow in which it is placed and runs another subflow. When the second subflow completes, the flow reverts to the original subflow to continue running. These subflows are often used in conjunction with conditionals.

## Flow control actions

To enter a comment for reference purposes which is displayed in the workspace, use the **Comment** action. Comments facilitate flow design, and allow users to make notes and explain the logic of action implementation and flow design.

![Screenshot of the Comment action properties dialog.](..\media\comment-action-properties.png)

Direct the flow to a specific point in the flow marked with the **Label** action. Provide a name for the label. 

![Screenshot of the Label action properties dialog.](..\media\label-action-properties.png)

Use a **Go to** action and select the label from a drop-down list to direct the flow to it.

![go to action properties](..\media\go-to-action-properties.png)

 To run another subflow at any point in the flow, use the **Run subflow** action. When the subflow completes, the flow continues with the next action. The subflow must be specified by name and can be selected from the drop-down list of existing subflows.

![Screenshot of the Run subflow action properties dialog.](..\media\run-function-action-properties.png)

To stop the subflow and go back to the point where it was run from, use **Exit subflow**. This action does not have properties. The **Exit Subflow** action is not required at the end of a subflow. When all the actions in a subflow have run, the flow will continue from the point where the subflow was run.

To stop running the entire flow, use the **Stop flow** action. To stop the flow with an error message, set **End flow** to **With error message** and specify the message to display.

![stop flow action properties](..\media\stop-flow-action-properties.png)

Place actions that are likely to fail or produce an erroneous result in an error block. The **On block error** action along with its corresponding **End** action are used to create an error block. Place actions in an error block to prevent the entire block from attempting to complete in the event that at least one of the actions within it fails.

Configure the properties to perform any combination of the described operations upon encountering an error inside the block in the following table:

|Operation                  |Description     |
|---------------------------|----------------|
|Set variable|Specify a variable and the value to set, or set a value to a new variable.|
|Run subflow|Specify which subflow to run from the list of subflows.|
|Go to next action  |Continue running the flow from the action that immediately follows the action that produced an error in the exception block. |
|Repeat action       |Retry the action that produced an error. |
|Go to label | Continue running the flow from a specified label. |
|Go to beginning of block   |Direct the flow to retry the actions inside the exception block from the start. |
|Go to end of block         |Direct the flow to the end of the block. |

![Screenshot of the On block error action properties dialog.](..\media\begin-exception-block-action-properties.png)
