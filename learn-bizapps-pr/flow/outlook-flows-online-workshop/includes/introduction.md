In a previous lab, you created a sample cloud flow that can run a desktop flow on your computer and then enter the invoice information for Contoso Coffee shop. However, you'll need to manually trigger that cloud flow to run every time. The Contoso Coffee shop uses Microsoft Outlook email to receive incoming invoices from different vendors as attachment files. Therefore, your next task is to build a new cloud flow that automatically triggers whenever an email arrives to that inbox. To do so, you'll need to use an Outlook connector in the cloud flow.

You'll complete the following tasks in this lab:

-   Create a new solution to package the end-to-end invoice processing solution.

-   Create a new cloud flow that initiates the invoicing process through the receipt of an email.

-   Integrate the desktop flow from Lab 2 into the cloud flow.

-   Perform a test run of the new cloud flow.

## Prerequisites
Before you begin the exercises in this lab, make sure that you meet the following prerequisites:

- Complete the first module in this Learning Path **Install required software - Online workshop**.

- Complete the module **Integrate with cloud flows - Online workshop** or import the provided solution in the resources folder

> [!NOTE]
> To complete the exercises, you'll need to use a few
> files. Download the [Automation in a Day files](https://pahandsonlab.blob.core.windows.net/documents/AutomationIAD-Learn-student-files.zip)
> for use in this module. Extract the contents of this download to your local computer. This is the same download from the previous modules for this online workshop.
