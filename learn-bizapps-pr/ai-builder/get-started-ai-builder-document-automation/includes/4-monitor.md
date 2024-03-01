In this unit, you will

- Learn how documents are received and processed.

- Understand how validator can monitor incoming documents for review.

- Assess how validator can review and edit processed documents.

- Learn how the admin can monitor the entire processing and act.

- Assess to get further by adding approvals, export to target system, and automatic validation steps.

## Monitoring and reviewing processed documents

The targeted person for monitoring and reviewing documents should:

- Have good business acumen.

- Understand which data must be extracted and eventually imported into a target system.

Business users are usually a good fit for this task.

1. When launching the **Document Automation Application**, validators will see only the **Processed** documents. You may also notice that the **Configuration** tab is hidden so only Makers can change the model to use.

   > [!div class="mx-imgBorder"]
   > [![List of documents for review (empty).](../media/4-documents.png)](../media/4-documents.png#lightbox)

1. As soon as documents arrive in the service email box, the **Document Automation Email Importer** flow detects the new email, extracts the attachment, calls the AI model and saves the extracted data as a pending process to be reviewed.

   > [!div class="mx-imgBorder"]
   > [![List of documents for review with invoice image documents for manual review.](../media/4-document-automation-email-review.png)](../media/4-document-automation-email-review.png#lightbox)

1. By selecting the document name, you can access details, review extracted fields and edit incorrectly extracted values. Select **Validate** to save your changes. You can also skip this document and navigate to the next one to be reviewed with the **Next document** button.

   > [!div class="mx-imgBorder"]
   > [![Manual review of invoice image showing extracted data for validation.](../media/4-validate.png)](../media/4-validate.png#lightbox)

1. The Maker has access to all documents including the ones in error and validated status.

   > [!div class="mx-imgBorder"]
   > [![List of documents including those with Validated or Invalid Document status.](../media/4-power-user.png)](../media/4-power-user.png#lightbox)

## Limitations

Export is not yet implemented in the **Document Automation Application**. If you want to export the extracted data, go to the **Power Apps Data** > **Tables** menu and **Document Automation Data** table, then at the top, select the button **Export data**.

> [!div class="mx-imgBorder"]
> [![Tables > Document Automation Data showing the Columns tab.](../media/4-limitations.jpg)](../media/4-limitations.jpg#lightbox)

You are now ready to automate the processing of your documents using AI and Microsoft Power Platform.
