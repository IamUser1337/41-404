The **Loop Condition** action is used when a block of actions should be repeated until a certain condition is met - this allows flows to repeat actions without prior knowledge of the number of repetitions required.

To demonstrate this functionality, we'll automate a flow which adds the employees’ expenses, and stops when the budget has been exceeded.

First, we'll initialize the running budget at 0, set the starting Excel line to 2, and open the file:

![Screenshot of the workspace example.](..\media\workspace-example-2.png)

Next, we'll add the loop condition, so that it ends when the budget exceeds 10000:

![Screenshot of the Loop condition action properties dialog.](..\media\loop-condition-action-properties-continued.png)

Within the loop, the flow will read the amount, add it to the running budget, and increase the index in order to move on to the next row:

![Screenshot of the loop condition workspace example.](..\media\loop-condition-workspace-example.png)

## Exit loop

As developed, this loop will only end when the budget exceeds 10000. However, if the sum of all expenses doesn't exceed the limit, then the loop will never end.
This is a good opportunity to examine the use of the **Exit loop** action. Before reading a cell’s contents, we should check if the Excel index has exceeded the range of the data.

If all data has been read and the limit hasn't been exceeded, then we'll assign the value **False** to the **%Exceeded%** variable and exit the loop, since there's no more data to read. We'll also initialize the **%Exceeded%** variable to **True** in the beginning, since, in all other scenarios, the limit will be exceeded:

![Screenshot of the loop condition if workspace example.](..\media\loop-condition-if-workspace-example.png)

Finally, we'll add an **If** action to check the **%Exceeded%** variable, and print a message accordingly:

![Screenshot of the completed loop condition if workspace example.](..\media\loop-condition-if-workspace-example-2.png)
