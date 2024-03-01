In previous modules, you created a cloud flow for Contoso Coffee shop that triggers when you receive a new email with an invoice file attachment in the Microsoft Outlook inbox. It uses AI Builder to parse data information out of the invoice file attachment and uses that information to enter the Contoso Coffee shop invoice management desktop app through a desktop flow.

Now, the Contoso Coffee shop company can use this automation to process invoices automatically, and they don't need to manually check email or enter data step by step. However, the Contoso Coffee shop company wants to make sure that the automation doesn't send payments to vendors automatically because it has financial consequences. The company wants a human supervisor to approve and confirm that the invoice is real and ready for payment before the automation can move to the next step. Microsoft Power Automate provides seamless, built-in human approval mechanisms that they can use for those types of scenarios.

In this module, you'll complete the following tasks, which completes the end-to-end invoice processing solution:

- Integrate a Microsoft Teams-based approval model and the associated conditional logic into the invoice processing cloud flow.

- Integrate the desktop flow for entering the invoice information into the approval process.

- Integrate Outlook-based approval/rejection notifications into the invoice process.

- Perform a test of the end-to-end invoice processing cloud flow.

> [!NOTE]
> To complete the exercises, you'll need to use a few
> files. Download the [Automation in a Day files](https://pahandsonlab.blob.core.windows.net/documents/AutomationIAD-Learn-student-files.zip)
> for use in this module. Extract the contents of this download to your local computer. This download is the same one that you used in the previous modules.
