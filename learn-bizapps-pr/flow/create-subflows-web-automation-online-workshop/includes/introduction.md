In previous modules, you created a cloud flow that's triggered to run automatically whenever a new invoice email arrives at the Contoso Coffee shop company email inbox. This cloud flow extracts the invoice details data from the attachment invoice file by using AI Builder, and then it sends an approval request to a human supervisor to confirm that it's real and ready to process. Then, the cloud flow runs a desktop flow to enter the invoice details in the Contoso Coffee shop invoice management desktop app. Finally, the cloud flow responds with confirmation to the vendors who sent the invoice. This module completes an end-to-end automation to process the incoming vendor invoices for Contoso Coffee shop.

In this module's scenario, you've learned that Contoso Coffee shop also needs to complete another step after processing a new incoming invoice. They need to record the invoice information into an existing Microsoft Excel file, which other departments use for auditing purposes. Furthermore, if you're working in an international branch in Europe, you're required to convert the invoiced amount from USD to EUR by using a real-time currency conversion rate, and then you'll need to log the converted amount into the Excel file. The Microsoft Power Automate for desktop app can also help you complete this type of task because it can automate against Windows applications and against any website. 

You'll complete the following tasks in this module:

- Exercise - Build a Power Automate Desktop subflow to write notes into Excel

  - Create a process with fixed value variables.

  - Test and run the process.

- Exercise - Build web automation by using Power Automate for desktop

  - Scrape web data and write to Excel.

  - Test and run the process.

> [!NOTE]
> To complete the exercises, you'll need to use a few
> files. Download the [Automation in a Day files](https://pahandsonlab.blob.core.windows.net/documents/AutomationIAD-Learn-student-files.zip)
> for use in this module. Extract the contents of this download to your local computer.
