As mentioned before, actions within a flow are run sequentially. However, there are certain actions that may alter this sequence, to achieve greater flexibility and adaptability while running a flow.

In this unit, we will examine two main categories of such actions: **Conditionals** and **Loops**.

## Conditionals

Conditional actions allow flows to modify their behavior during runtime, based on the data available at the time. Essentially, they allow flows to make choices based on the information at their disposal.

In the previous example, we can add a Conditional action to modify the flow's behavior based on the contents of the first cell.

We will add an **If** action to the workspace, configuring it as below:

![Screenshot of the If action properties dialog.](..\media\if-action-properties.png)

We want to check whether the variable that contains the data we read from the worksheet in the previous action contains the desired header.

> [!NOTE]
> Selecting the variable icon next to the input field will produce a list of available variables to add to the field; this makes variables easier to handle.
>![Screenshot of the variable icon and variable list.](..\media\variable-icon.png)

Press **Save** to add the action to the workspace. An **End** action is also automatically added, to signify the end of the conditional block of actions; any actions added between the **If** and **End** actions will only run if the condition in the **If** action is met.

We will add a **Write to Excel worksheet** action to test this. If the header is not correct, we would like to write it in:

![Screenshot of the Write to Excel worksheet action properties dialog.](..\media\write-to-excel-worksheet-action-properties.png)

![Screenshot of the actions workspace with the If action added.](..\media\actions-workspace.png)

## Loops

Loops enable flow to repeat a block of actions multiple times. The number of repetitions is determined by the type of loop action used and its configuration.

Let’s expand the current example by adding Row IDs up to row 10; to achieve this, we will use the **Loop** action.

The **Loop** action initializes an index variable, and repeats until said variable reaches a specified value. The index variable is incremented by a certain value with each repetition:

![Screenshot of the Loop action properties dialog.](..\media\loop-action-properties.png)

Configured as above, the variable **%LoopIndex%** will be initialized to 2, and will be incremented by 1 each time the loop repeats, until it reaches the value 10.

When we add the **Loop** action, an **End** action is also automatically added to the workspace; this is analogous to the **End** action in the previous unit.

Between the **Loop** and **End** actions, we will add a **Write to Excel worksheet** action, which will write the ID in each row:

![Screenshot of the Write to Excel worksheet action properties dialog with parameters filled in.](..\media\write-to-excel-worksheet-action-properties-continued.png)

![Screenshot of the actions workspace with the Loop added.](..\media\actions-workspace-continued.png)

In this case, the loop index is used both to determine the row in which the flow will write, and the contents to be written. When this loop runs, all rows from 2 to 10 will contain the numbers 1-9 in column A.
