All custom form elements and actions possess a unique ID that identifies them uniquely in the desktop flow.

To examine how you can use these IDs to access data in other actions, create a form with the following elements:

- A text input with the value **NameInput** as an ID. Populate the value **Name** to the **Label** field and set the input to be required.

- A text input with the value **LastNameInput** as an ID. Populate the value **Last Name** to the **Label** field and set the input to be required.

- A date input with the value **DateBirthInput** as an ID. Populate the value **Date of Birth** to the **Label** field and set the input to be required.

- Α submit action with the value **Submit** as an ID and **Save** as a title.

- Α submit action with the value **Cancel** as an ID and title. Enable the **Ignore provided input** option to set the action function as a cancel button.

![Screenshot of the deployed custom form elements.](..\media\custom-form-designer-exercise.png)

After designing the form, use the appropriate Excel actions to launch an Excel spreadsheet, find the first free row in it, and populate the provided user data.

![Screenshot of the deployed Excel actions.](..\media\excel-actions.png)

When a user populates the form, the provided data are stored in the **CustomFormData** custom object variable. To access the value of a specific input element stored in the custom object, use the following notation: **%CustomFormData['ElementID']%**.

In this scenario, use three **Write to Excel worksheet** actions to write the provided name, last name, and date of birth. 

> [!NOTE]
> The Excel spreadsheet must contain three columns for the  name, last name, and date of birth, respectively.

To achieve that, populate the **Value to write** field with the following expressions:

- **%CustomFormData['NameInput']%**, for the name
- **%CustomFormData['LastNameInput']%**, for the last name
- **%CustomFormData['DateBirthInput']%**, for the date of birth

![Screenshot of the Write to Excel worksheet action that writes the name.](..\media\write-excel-worksheet-action.png)

The current desktop flow tries to write the custom form values to the Excel spreadsheet regardless of the selected button (Save or Cancel).

To run this part of the flow only when the save action is pressed, enclose the actions in an **If** block. 

Like the other elements, each action has an ID that describes it uniquely. When an action is selected, its ID is stored in the **ButtonPressed** variable.

Use the **If** action to check whether the **ButtonPressed** variable contains the value **Submit**. If it does, the user has selected the save action, and the flow can populate the provided data in the Excel spreadsheet.

![Screenshot of the If action that checks which button is pressed.](..\media\if-action.png)

The final flow should look like the one in the following screenshot:

![Screenshot of the final desktop flow.](..\media\final-desktop-flow.png)