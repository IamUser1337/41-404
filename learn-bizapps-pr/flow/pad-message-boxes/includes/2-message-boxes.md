Message boxes enable real-time interaction between users and flows. Message boxes actions can be used both to provide input to flows and provide output to the users.

## Output actions

To examine how the output message boxes function, replicate the following flow that extracts data from an Excel file and populates it into a web portal.

> [!NOTE]
> The **Populate_Web_Form** subflow should contain all the functionality to populate the Excel data into the web portal. For this example, you can use any web portal for which you have access rights.

![Screenshot of the output function workspace.](..\media\output-function-workspace.png)

Depending on the data size and the processing steps for each entry, the flow may take significant time to complete. When the flow is finished, add a message box to inform the user that the flow has finished successfully and display the number of claims processed.

![Screenshot of the Display message action properties.](..\media\display-message-action-properties.png)

In the following screenshot, you can examine how the **Display message** action affects what the user sees when the flow runs successfully.

![Screenshot of the message box showing the number of claims processed.](..\media\message-box.png)

## Input actions

The second function of message boxes actions is enabling users to provide input to the flow.

User input may come in many forms, such as text, datetime, files and folders, etc. Each of these input types corresponds to a different message box action.

As an example, examine the following flow that requires a file path and a multi-line text as input from the user and appends the text input to the file.

![Screenshot of the input function workspace.](..\media\input-function-workspace.png)

The following **Display select file dialog** action displays a dialog for the user to select a .txt file.

![Screenshot of the Display select file dialog action properties.](..\media\display-select-file-dialog-action-properties.png)

The **Display input dialog** action is configured to receive a multi-line text as input.

![Screenshot of the Display input dialog action properties.](..\media\display-input-dialog-action-properties.png)

In the following screenshot, you can see the dialog produced by the **Display input dialog** action.

![Screenshot of a multi-line text message box.](..\media\text-input-dialog.png)

## Custom forms

As presented in the previous sections, you can use the input and output message boxes for scenarios where a single input or output is required, respectively.

However, some automation scenarios may require a combination of multiple inputs or/and outputs. The best approach to implement this functionality is creating a custom form.

To create a custom form, deploy the **Display custom form** action and press the **Custom form designer** button to open the form designer.

![Screenshot of the Custom form designer button in the Display custom form action.](..\media\display-custom-form-action.png)

The designer provides a variety of input elements, such as text, date, and file inputs, and some non-interactive elements, such as texts and images.

All input elements are identified by a unique ID that you can use to access the provided data later in your flow. The data are stored in the **CustomFormData** custom object variable, and you can use the following notation to access them: **%CustomFormData['ElementID']%**.

![Screenshot of a selected text input element.](..\media\text-input-element.png)

Apart from these elements, the custom form designer provides actions that enable you to implement additional functionality to your form.

The submit action allows you to gather the data provided by the user or use it as a cancel button. When an action is pressed, its unique ID is saved into the **ButtonPressed** variable. If your form contains many actions, use this variable and conditionals to implement different flow behavior for each scenario.

![Screenshot of a flow checking which form button has been pressed.](..\media\custom-form-example.png)