If you've installed Microsoft Outlook on your desktop, Power Automate for desktop enables you to automate it using the Outlook actions.

These actions can launch and close Outlook, as well as retrieve, send, process and save emails from all the connected accounts. The ability to handle multiple accounts in the same flow allows you to handle emails from multiple sources and manage all your accounts simultaneously.

## Launch and close Outlook

Before deploying any Outlook actions, use the **Launch Outlook** action to launch Outlook and create an instance variable of it. This action doesn't require any parameters, while the other Outlook actions require the created instance.

![Screenshot of the Launch Outlook action dialog.](..\media\launch-outlook-action.png)

When you no longer need the created instance in the flow, deploy the **Close Outlook** action to close it.

![Screenshot of the Close Outlook action dialog.](..\media\close-outlook-action.png)

## Retrieve email messages from Outlook

To retrieve emails that meet specific criteria from an Outlook folder, use the **Retrieve email messages from Outlook** action.

To limit the retrieved emails, you can filter them according to their parent folder, state, or keywords included in various fields. If the retrieved emails contain attachments, the action allows you to save the files locally on your desktop.

![Screenshot of the Retrieve email messages from Outlook action dialog.](..\media\retrieve-emails-outlook.png)

## Send email message through Outlook

To send an email message through Outlook, deploy the **Send email message through Outlook** action, that creates and sends new email messages. In the action's properties, you can specify the following elements:

- Sender
- Recipient
- CC and BCC recipients
- Subject and body of the new email

Optionally, you can write the email body in HTML and attach files to the message. To attach a file, populate the file path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

![Screenshot of the Send email message through Outlook action dialog.](..\media\send-email-outlook.png)

## Process email messages in Outlook

After retrieving messages from a mailbox, Power Automate for desktop enables you to manipulate them through the **Process email messages in Outlook** action.

This action runs a series of essential email handling operations, such as deleting, marking as unread, and moving messages to other folders.

To use this action, you have to set a list of emails as input. This list can be created by the **Retrieve email messages from Outlook** action.

![Screenshot of the Process email messages in Outlook action dialog.](..\media\process-emails-outlook.png)

## Save Outlook email messages

Apart from processing retrieved emails, Power Automate for desktop enables you to save emails locally using the **Save Outlook email messages** action.

This action requires a list of emails that can be retrieved using the **Retrieve email messages from Outlook** action.

You can save the extracted emails into various file types, such as Outlook Message, HTML, and text. To name the files manually, select **Custom** in the **File name** dropdown menu and populate the **Save as** field.

![Screenshot of the Save Outlook email messages action dialog.](..\media\save-emails-outlook.png)

## Respond to Outlook message

To reply or forward an email, use the **Respond to Outlook message** action. This action responds to an Outlook message by replying, replying to all, or forwarding.

In the action's properties, you have to populate an email variable. You can use an individual element of an email list retrieved with the **Retrieve email messages from Outlook** action.

Apart from text, the action allows you to attach files to your replying message. To attach a file, populate the file path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

If you select to forward an email, you should also populate the primary recipient, as well as the CC and BCC recipients.

![Screenshot of the Respond to Outlook message action dialog.](..\media\respond-email-outlook.png)
