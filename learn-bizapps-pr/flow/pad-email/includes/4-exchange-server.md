If your organization uses an Exchange server, Power Automate for desktop enables the automation of it through the Exchange actions. You can use the Exchange actions to connect to an Exchange server and retrieve, send, or process emails from it.

## Connect to an Exchange server

Before deploying any Exchange actions, use the **Connect to Exchange server** action to establish a connection with a selected Exchange server.

In the action's properties, you can set the Exchange server's version and select whether the server will be detected automatically through the email address.

Additionally, you can choose between setting the credentials to the Exchange default or specifying them manually. The action stores the established connection to a variable for late use in other Exchange actions.

![Properties of the Connect to Exchange server action dialog.](..\media\connect-exchange-action.png)

## Retrieve Exchange email messages

To retrieve emails that meet specific criteria from an Exchange folder, use the **Retrieve Exchange email messages** action.

To limit the retrieved emails, you can filter them according to their parent folder, state, or keywords included in various fields. If the retrieved emails contain attachments, the action allows you to save the files locally on your desktop.

![Properties of the Retrieve Exchange email message action dialog.](..\media\retrieve-exchange-action.png)

## Send an Exchange email message

To send an email message, deploy the **Send Exchange email message** action, that creates and sends new email messages through a previously established Exchange server connection.

In the action's properties, you can specify the following elements:

- Sender
- Sender's display name
- Recipient
- CC and BCC recipients
- Subject and body of the new email

Optionally, you can write the email body in HTML and attach files to the message. To attach a file, populate the file path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

![Properties of the Send Exchange email message action dialog.](..\media\send-exchange-action.png)

## Process Exchange email messages

After retrieving messages from an Exchange folder, Power Automate for desktop enables you to manipulate them through the **Process Exchange email messages** action.

This action runs a series of essential email handling operations, such as deleting, marking as unread, and moving messages to other folders.

To deploy this action, you have to set a list of emails as input. This list can be created by the **Retrieve Exchange email messages** action.

![Properties of the Process Exchange email messages action dialog.](..\media\process-exchange-action.png)
