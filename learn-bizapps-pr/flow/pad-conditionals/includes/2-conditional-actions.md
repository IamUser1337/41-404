Conditionals are used to modify a flow's behavior based on certain conditions. Conditions may include the comparison of two values, or more specific information, such as the existence of a file or the contents of a web page.

Conditional actions are divided into two major categories in Power Automate for desktop, based on their functionality. These are:

* The **If** group of actions
* The **Switch** group of actions

## If group of actions

The **If** group of actions allow users to evaluate whether a certain condition is true. The structure of an If conditional is as below:

* Initial condition
* Alternative conditions (0 or more)
* Unconditional alternative (optional)
* End of conditional block

Thus, the simplest If structure is as below:

![Screenshot of the simplest If structure.](..\media\simplest-if.png)

![Screenshot of If dialog with parameters set to UrgentCell equals Urgent.](..\media\if-cell-contains-urgent.png)

Configured this way, Action #2 will only run if the %UrgentCell% variable contains the value **Urgent**.

Some initial conditions in the If group are **If**, **If File Exists**, **If Window Contains**, **If Text on-Screen** actions. All conditional blocks in the **If** group end with the **End If** Action.

Alternative conditions may be added using the **Else If** Action; these conditions will only be considered if all the previous conditions were false. For example, in the flow below, the Subscription cell will only be selected if the initial condition is not met; in this case, if the %UrgentCell% variable does not contain the value **Urgent**:

![Screenshot of the If UrgentCell = urgent, then write 12 hours, Else if SubscriptionCell = premium, then write 1 day action.](..\media\else-if-action.png)

Multiple alternative conditions can be added, and these conditions do not necessarily have to be related.

An unconditional alternative may also be added, using the **Else** Action; this will run if all the conditions before it have failed:

![Screenshot of the same action with an Else action added.](..\media\else-action.png)

## Switch group of actions

The **Switch** group of actions is designed to evaluate a single variable and compare it to other values. **Switch** and **If** actions vary in the following ways:

* **If** blocks allow more than one variable to be evaluated and compared with others; **Switch** checks a single variable
* **If** actions may be used to evaluate more than the value of a variable (for example, checking whether folders or files exist, checking values of web page or window content); **Switch** actions work only with values and variables.

The structure of a **Switch** conditional is:

* Initial value input
* Alternative cases (1 or more)
* Unconditional case (optional)
* End of conditional block

Thus, the simplest **Switch** structure is:

![Screenshot of the Simplest switch action.](..\media\simplest-switch.png)

![Screenshot of the Switch action property dialog with Value to check set to UrgentCell.](..\media\switch-cell-contents.png)

![Screenshot of Case action property dialog with Value to compare set to Urgent.](..\media\case-action.png)

As with the **If** group of actions, the **Write to Excel Worksheet** action will only run if the %UrgentCell% variable contains the value **Urgent**.

Each Switch block begins with the **Switch** action and ends with an **End Switch** action. Alternative cases are added within the Switch block, using the **Case** and **End Case** actions.

Multiple alternative conditions can be added; these conditions will all refer to the variable specified in the **Switch** action.

An unconditional alternative may also be added, using the **Default Case** action; as was the case in the **If** group of actions, this will run if no other **Case** action before it runs:

![Screenshot of a completed Switch Case and Default case action.](..\media\default-case.png)
