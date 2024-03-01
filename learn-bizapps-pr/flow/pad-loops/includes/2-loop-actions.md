Loops are used to repeat a block of actions multiple times, in order to automate repetitive tasks. The number of repetitions depends on the type of loop that will be used, as well as the size of the dataset that needs to be processed.
There are three distinct types of loops:

* Simple loop
* For Each loop
* Loop Condition

Each of these loop types allows the repetition of a block of actions - what sets them apart is the way they are configured, and the scenarios in which they are used.

## Simple loops

The **Loop** action allows the creation of simple loops. Simple loops use a loop index variable - it's assigned an initial value, an end value, and an increment value. When the loop begins, the index is assigned its initial value, and every time a repetition ends, the increment value is added to the index - if the index has reached or surpassed its end value, the loop ends, otherwise it repeats.

The **Loop** action is most commonly used when the number of repetitions required is known beforehand, or when an index value is required within the Block of actions that are repeated – for example, when iterating a list or table.

When configured as below, the loop will repeat **%ClientNumber%** times:

![Screenshot of the Loop action properties dialog.](..\media\loop-action-properties.png)

## Loop condition actions

The **Loop Condition** action is designed to repeat as long as a specified condition is true. When a repetition ends, the condition is evaluated; if it’s true, then the loop repeats, otherwise it ends.

The **Loop Condition** action is mostly used when the number of required repetitions is not known, and depends on a certain condition being met.

When configured as below, the loop will keep repeating until the total budget is greater than 10000:

![Screenshot of the Loop condition action properties dialog.](..\media\loop-condition-action-properties.png)

## For Each loop

The **For Each** action iterates through a list or table of items, and repeats once for each item. The loop will end when it has iterated through all the items of the list or table it received as input.

The **For Each** action is most often preferred when a task must be repeated using data in the form of lists or tables.

In the following example, the loop will repeat once for each file in the given list:

![Screenshot of the For each action properties dialog.](..\media\for-each-loop-action-properties.png)

## End loop

The **End Loop** action is automatically added when any of the above three loops are used, and marks the end of the block of actions that should be repeated:

![Screenshot of the for each loop example workspace.](..\media\for-each-loop-example-workspace.png)

In the above example, actions 4-6 will be repeated for each email message stored in the **%RetrievedEmails%** list.

## Exit loop

The **Exit Loop** action is used to immediately exit a loop, regardless of whether its end condition has been met. This action permits Users to immediately end a loop in certain cases where this is required.

**Exit Loop** must be placed within a loop block, and is always used within a conditional:

![Screenshot of the exit loop action workspace.](..\media\exit-loop-action-workspace.png)

In the above scenario, the loop will end when the total budget is greater than 10000 – however, if the flow encounters a non-positive number, indicating that there is no more data to add, the loop will end immediately.
