The last step in working with a **Form** control is to submit the edits. To do this we use the **SubmitForm** function. This function is often placed on a **Button** control labeled **Save** or **Submit**. The formula for **OnSelect** is **SubmitForm(YourFormName)**.

This function takes all of the data that is entered into the controls on your data cards and save it to the data source for the **Form** control. Each data card on your **Form** control has an **Update** property
specifying the data, in formula form that will be written to the data source when **SubmitForm** is called. If you have unlocked your card, you can modify that formula. This is often unnecessary and only done in special circumstances.

>[!Important]
>When you begin modifying card formulas, you need to match the data type that your source is expecting or you may receive an error and your data entry may not save properly.

## After you submit your form

The **Form** control is easy to use because with invocation of the **SubmitForm** function your data is whisked away and your data source is updated. The **Form** control has three properties that process after the data is
submitted based on the outcome of the submission. These properties are **OnSuccess**, **OnFailure**, and **OnReset**. Additionally, the **LastSubmit** property provides you with a record of what data was submitted from the form.

>[!Note]
>If you want submitting your form to do something else, such as navigate to another screen, add the coding into one of these three form properties. Don't add additional code to whatever button, icon, or function invokes the **SubmitForm** action.

For each of these properties, you can enter a formula. For example, if you want the user to go to a different screen after their data is submitted successfully, then in **OnSuccess** you would use the function
**Navigate(SuccessScreen, ScreenTransition.Cover)** to send them to the screen named **SuccessScreen**.

### OnFailure property

Use the **OnFailure** property if there's an error when the data is submitted. You could use a formula to specify a warning message that appears when the failure occurs. The following formula is an example of using the **Notify** function to provide more info to the user.

```Power Apps formula
Notify("Your data was not saved. Please try again or contact an administrator.", NotificationType.Error)
```

This function would display a red warning at the top of the screen with the message "Your data wasn't saved. Try again or contact an administrator." This message makes it easier for the user to resolve the issue.

### OnReset property

Use the **OnReset** property if the form is reset. A form reset occurs when the **ResetForm** function is used. The **ResetForm** function sets the form back to its default values and then runs any formula specified in the **OnReset** property. An example would be if you wanted to reset a **Variable** or **Timer** control used with interacting with the form.

### LastSubmit property

After your form submits successfully, you can reference the submitted record directly. The last submitted record is available using the **LastSubmit** property that contains the entire record. You can access the record by using the formula **FormName.LastSubmit** (substitute your form's name for *FormName*). You can also access an element from the LastSubmit record by inserting a **Label** control into your app, and then using a formula such as: **FormName.LastSubmit.ID** which returns the **ID** property of the last record submitted. Understanding **LastSubmit** is a powerful concept as you start to build relational data where you need to know the value from a previous form submission.

In the next unit, we'll discuss some valuable Special properties of the form control.
