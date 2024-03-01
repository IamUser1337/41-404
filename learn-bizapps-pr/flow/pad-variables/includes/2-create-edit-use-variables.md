Power Automate for desktop automatically produces all the necessary variables that actions need, while it also enables you to create variables manually.

In this unit, we'll present how to create variables and use them as input parameters in deployed actions.

## Creating and using variables

To prevent the declaration of unnecessary variables, Power Automate for desktop produces variables automatically for the deployed actions.

Every time you add a new action in the workspace, the platform automatically produces some variables that hold the results. If you want to change the default name of a produced variable, you can select it and populate the new name.  

![Screenshot of the produced variable of the Change text case action.](..\media\produced-variables.png)

In case you don't need a produced variable in your flow, you can select the toggle button on the left side of it to disable it. Disabling unused variables reduces the number of variables in the variables pane and makes management more efficient.

![Screenshot of the option to disable a produced variable.](..\media\disabled-produced-variables.png)

After creating a variable, you might need to use its content as input in other actions. To reuse a variable, select the icon next to the desired input field and pick the variable or a specific property of it.

![Screenshot of the button to select a variable as a parameter.](..\media\select-variable-button.png)

You can also use existing variables as outputs in actions, but the platform will overwrite their previous content.

> [!NOTE]
> Storing new data in an existing variable will overwrite its contents, and it may change its data type. It's a good practice to use new variables for different results to keep your flows clear and robust.

## Variables pane

Power Automate for desktop displays all the necessary information about the created variables in the variables pane.

The variables pane is located next to the workspace and enables you to review and manage variables. Through the variables pane, you can create and handle two different kinds of variables: input/output variables and flow variables.

As you can assume by their name, input/output variables enable you to pass data to and from the Power Automate platform. This feature creates unlimited automation potentialities allowing you to make the most out of the platform.

> [!NOTE]
> If you are interested in passing data to and from the Power Automate platform, you can check the respective course.

All the variables you use locally in your flows are called flow variables, and you can access them only through this particular flow.

![Screenshot of the Power Automate for desktop variables pane.](..\media\variables-pane.png)

Regardless of the type of the used variables, you can display additional information about them by clicking on their name.

Except for the type and the contents of the variables, you can use the variable pane to see all their available properties. Properties contain parts of the information stored in the variable or an extra attributes describing the variables.

While you are debugging your flows using the **Run next action** button, you can check each variable's current value through the variables pane. Seeing how the flow changes the variables' contents in real time allows you to locate the source of unwanted functionality.

![Screenshot of the displayed variable's information.](..\media\variable-information.png)

Besides providing information about the variables, the pane also allows you to perform more complicated tasks, such as renaming and finding where each variable is used.

If you want to rename a variable, right-click on it and select **Rename**. To locate where a variable is used in your flow, select **Find usages** in the same menu.

![Screenshot of the Rename and Find usages options of the variable.](..\media\rename-find-usage-variable.png)

In case you have developed complicated flows with numerous variables, you can use the filter button to filter the displayed variables. Displaying variables of specific data types makes searching quicker and more efficient.

![Screenshot of the filter button in the variables pane.](..\media\variables-filter.png)
