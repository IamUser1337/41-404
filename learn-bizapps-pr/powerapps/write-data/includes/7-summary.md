Forms are a valuable tool for app development, providing a quick way to interact with your data. Forms allow you to view, edit, and create new records in your data source. In this module, you focused on the different form modes, how to customize a form, and how to submit data and special properties for working with forms. These items are important to remember:

- Use the **Edit form** control if you want to view or edit an existing item or add a new item. If you only want to view an item you can use the **Display form**, although it has fewer customization options.

- You must specify the record that you want to return in the form control. The two most common ways of returning a record are by connecting the **Form** control to a **Gallery** control's selected property or by using a **LookUp** function.

- Based on the outcome of the submission, use the **OnSuccess**, **OnFailure**, and **OnReset** properties to run formulas after submission. **LastSubmit** provides information about the last record you submitted.
