While developing flows, it's common to reuse information in multiple actions and update it based on certain conditions. For example, you might need to store some retrieved emails and process them later in your flow.

Power Automate for desktop enables you to store this information for later use through variables. Variables provide a way of labeling data with a descriptive name and allow you to refer to it by name.

You can think of variables as storage bins that save valuable information while a flow is running. The stored information can be virtually any type, such as numbers, text, dates, or files and folders.

In order to use variables as input parameters in actions, you have to enclose their names in percentage characters. Using this notation, you command the platform to interpret the value as a variable and not a hardcoded content.

For example, to use a variable named **CustomerName**, you have to populate the action's respective input parameter with the expression: **%CustomerName%**.

![Screenshot of a variable used as an action parameter.](..\media\variables-precentage-notation.png)

By the end of this module, you'll be able to use variables in your flows and create advanced automations with them.

## Learning objectives

In this module, you will:

- Create, edit, and manipulate variables.
- Examine the variables pane.
- Become familiar with various variable data types and their properties.
- Configure input and output variables.

## Prerequisites

- Basic familiarity with the Power Automate for desktop console and flow designer.
