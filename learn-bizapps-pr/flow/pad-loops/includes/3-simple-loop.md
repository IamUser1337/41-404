The Loop action is used primarily when a predetermined number of repetitions is required. Another common use of simple loops is tasks where the loop index is important to the task itself. Let’s examine both cases with an example.

Consider the following flow: an Excel file contains employees’ names and email addresses. From those email addresses, employees send their business expenses - these email messages will be retrieved, and each employee’s expenses will be added to their respective row in the Excel file.

First, we open the Excel report and determine the range of the data:

![Screenshot of the workspace example.](..\media\workspace-example.png)

Each of the rows, from 2 until the last populated row, contains the information of an employee (row 1 is not included, because it contains headers). We'll have to both read and write to these rows, so an index variable will have to be used. Therefore, we choose to use a loop action:

![Screenshot of the Loop action properties.](..\media\loop-action-properties-continued.png)

Within the loop, we set the sum of expenses to 0, read the employee’s email address, and retrieve the emails sent from their account to the designated one, with the subject line **Company Expense**:

![Screenshot of the workspace loop example.](..\media\workspace-loop-example.png)

 ![Screenshot of the Retrieve emails action properties dialog.](..\media\retrieve-emails-action-properties.png)

Finally, the email’s body, containing the expense amount, will be written into the respective cell. Since only one email message is expected, we will use the body of the first (and only) email in the list of retrieved emails:

![Screenshot of the completed workspace loop example.](..\media\workspace-loop-example-continued.png)

Note that both reading the email address, and writing the expense amount (actions 5 and 7) require the use of the loop index variable. This ensures that each repetition of the loop will access a different row in the Excel file.
