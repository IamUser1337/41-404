In this exercise, you'll develop a flow that sends confirmation emails to received support tickets from customers.

To execute the flow of the exercise successfully, use the credentials of a valid webmail account. If the account or server information is false, the flow will fail.

1. Launch the Power Automate for desktop console and create a new flow named **Ticket confirmation**.

    ![Properties of the Build a flow dialog with the Flow name highlighted.](..\media\exercise-new-flow.png)

1. Deploy a **Retrieve email messages** action and configure it to retrieve all the unread emails that contain the word **Ticket** in their subject line. Populate the **Mail folder** field with the main inbox folder of your account.

    ![Properties of the Retrieve email messages action dialog.](..\media\exercise-retrieve-emails-action.png)

1. To configure the IMAP server, expand the **IMAP server** section of the action and populate the appropriate server information.

    ![Properties of the IMAP server section of the Retrieve email messages action dialog.](..\media\exercise-retrieve-emails-action-imap.png)

1. Add a **For each** loop to the workspace and set it to iterate through the list that contains the retrieved emails.

    ![Properties of the For each action dialog.](..\media\exercise-for-each-action.png)

1. Inside the loop, add a **Parse text** action to get the email address part of the **%CurrentItem['From']%** property. To get this specific text part, use the **<(.*?)>** regular expression.

    ![Properties of the Parse text actions.](..\media\exercise-parse-text-action.png)

1. Below the **Parse text** action, add a **Send email** action to send an email to each ticket owner. Set the email subject to contain the subject of the received email with a confirmation notation. The body can optionally include a confirmation text.

    ![Properties of the Send email action dialog.](..\media\exercise-send-email-action.png)

1. Expand the **SMTP server** section of the action and populate the SMTP server's appropriate information.

    ![Properties of the SMTP server section of the Send email action.](..\media\exercise-send-email-action-smtp.png)

1. Beneath the **Send email** action, add a **Process email messages** action. Set it to move each retrieved email to a folder named **Confirmed tickets**.

    ![Properties of the Process email messages action dialog.](..\media\exercise-process-emails-action.png)

1. Expand the **IMAP server** section of the action and populate the IMAP server's appropriate information.

    ![Properties of the IMAP server section of the Process email messages action.](..\media\exercise-process-emails-action-imap.png)

1. Save the flow and run it to test that every action runs as expected.

    ![Properties of the final flow and the save and run buttons.](..\media\exercise-final-flow.png)
