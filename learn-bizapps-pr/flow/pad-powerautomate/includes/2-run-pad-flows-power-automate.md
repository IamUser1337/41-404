After creating your desktop flow in Power Automate for desktop, you can run it from a cloud flow in Power Automate, in either attended or unattended mode.

Create a desktop flow in Power Automate for desktop, and add input and output variables.

![Screenshot of the input output variables.](..\media\input-output-variables.png)

Input variables will retrieve their values from the ones provided in the Power Automate cloud flow.

![Screenshot of the Add new input variable dialog.](..\media\new-input-variable.png)

Values of output variables can be passed to the Power Automate cloud flow.

![Screenshot of the Add new output variable dialog.](..\media\new-output-variable.png)

The external name field determines the names the variables use in Power Automate. This way, you can avoid conflicts with existing variable names, as well as provide more UI-appropriate names for variables in Power Automate, depending on your requirements.

When running the desktop flow from the console, a dialog prompts the user for the values of the input variables.

   ![Screenshot of the Flow inputs variables dialog.](..\media\input-variable-dialog.png)

You can call this desktop flow to run from Power Automate.

## Run a Power Automate desktop flow from the Power Automate portal

1. Open a cloud flow in Power Automate and select **New step**

   ![Screenshot of the new step button below Manually trigger a flow.](..\media\new-step.png)

1. Search for and select the **Run a flow built with Power Automate for desktop** action.

   ![Screenshot of the Run a flow built with Power Automate for desktop action.](..\media\run-flow-built-by-pad.png)

1. Choose an existing desktop flow or create a new one, and select the run mode.

   Choosing a desktop flow with input variables will display fields where values for these variables can be entered. When the Power Automate desktop flow runs, it will use the values provided here.

   ![Screenshot of the Run a flow built with Power Automate for desktop action properties.](..\media\run-flow-pad-action-properties.png)

1. Edit the desktop flow by selecting **Edit**. Select **Launch app** in the confirmation dialog.

   ![Screenshot of the run Power Automate for desktop.](..\media\run-pad.png)

1. Your browser may prompt you to allow the launch of Power Automate for desktop. Select **Open** to continue.

   ![Screenshot of the browser launching Power Automate for desktop.](..\media\browser-launch-pad.png)

1. When the flow in the Power Automate for desktop flow designer is complete, save it, and select **Keep Working** in this dialog.

   ![Screenshot of the Launching Power Automate for desktop dialog.](..\media\pad-launched-dialog.png)

1. Actions in the Power Automate cloud flow can retrieve the values of output variables.

   ![Screenshot of the external Append to array variable.](..\media\external-variable.png)
