Power Automate for desktop enables the automation of webmail services through the email actions. You can use these actions to retrieve email messages from IMAP servers and send messages through SMTP servers.

Virtually all major webmail services support IMAP and SMTP, while they usually require you to activate the respective options.

> [!NOTE]
> To automate email accounts protected with multi-factor authentication, you have to create application passwords.

## Configure IMAP and SMTP servers

Before deploying any email actions, you have to configure the server that will handle the requests. The **Retrieve email messages** and **Process email messages**  actions require an IMAP server, while the **Send email** action requires an SMTP server.

To configure the required IMAP server, open the action's properties and expand the  **IMAP server** section.

In the **IMAP server** section, populate the address and the port of the server, and your account credentials. If untrusted certificates are permitted or the server uses TLS/SSL, select the **Accept Untrusted Certificates** or the **Enable SSL** option, respectively.

![Screenshot of the IMAP server section in the Retrieve email messages action.](..\media\imap-server-config.png)

To configure the required SMTP server, open the properties of the **Send email**  action and expand the **SMTP server** section.

In the **SMTP server** section, populate the address and the port of the server, and your account credentials. Additionally, you can enable SSL/TLS and untrusted certificates, if they're applicable.

![Screenshot of the SMTP server section in the Send email action.](..\media\smtp-server-config.png)

## Retrieve email messages

To retrieve emails that meet specific criteria from your mailbox, use the **Retrieve email messages** action.

To limit the retrieved emails, you can filter them according to their parent folder, state, or keywords included in various fields. All the available filters are located in the **Email filters** section of the action's properties.

If the retrieved emails contain attachments, the action allows you to save the files locally on your desktop.

![Screenshot of the Retrieve email messages action.](..\media\retrieve-emails-action.png)

## Process email messages

After retrieving messages from your mailbox, Power Automate for desktop enables you to manipulate them using the **Process email messages** action.

This action runs a series of essential email handling operations, such as deleting, marking as unread, and moving messages to other folders.

To deploy this action, you have to set a list of emails as input. The list can be created by the **Retrieve email messages** action.

![Screenshot of the Process email messages action.](..\media\process-emails-action.png)

## Send email

The last action of the email group is the **Send email** action, that creates and sends new email messages. To deploy this action, you have to specify the following elements:

- Sender
- Sender's display name
- Recipient
- CC and BCC recipients
- Subject and body of the new email

Optionally, you can write the email body in HTML and attach files to the message. To attach a file, populate the file path or a variable containing the file (or a list of files) in the **Attachment(s)** field.

![Screenshot of the Send email action dialog.](..\media\send-email-action.png)
