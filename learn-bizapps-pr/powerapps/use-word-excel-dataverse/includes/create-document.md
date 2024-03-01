You can create a Word template in Power Apps from two different areas:

-   **Advanced settings** - Using this area requires specific permissions that are available through the System Administrator or System Customizer security roles.

-   **From a specific record** - When the record is open (main form) or selected in a list (view), those templates are available only for the user who created them.

This module will focus on personal templates.

## Create a dynamic Word template

To create a Word template based on Dataverse, follow these steps:

1.  In a model-driven app, select a specific record from a view for a target table. From the **Word Templates** dropdown menu, select **Download Template**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a sample model-driven app, displaying a list of active accounts and the first record selected. Focus is on the Download Template option of the Word Templates dropdown menu.](../media/download-template.png)](../media/download-template.png#lightbox)

1.  In the displayed form, confirm or select another table (entity) and indicate if any records that are related to this table are required in the template (by using the different relationship options). Select **Download** to proceed to the next step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Download file to create a template form. Focus is on the Download option.](../media/download.png)](../media/download.png#lightbox)

1.  Open the generated Word template (downloaded on your local computer). If the **Developer** option isn't available in the menu, enable this option from **Files > Options**. Select **Customize Ribbon**, enable **Developer**, and then select **OK** to confirm.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Word Options form. Focus is on the Developer option under the Customize Ribbon section and on the OK option.](../media/developer.png)](../media/developer.png#lightbox)

1.  Define which fields are available for the template. To do so, select **XML Mapping Pane** on the **Developer** menu. Select the **Custom XML Part** that starts with **urn:microsoft-crm/document-template/**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Microsoft Word. Focus is on the XML Mapping Pane on the Developer menu. Focus is also on the Custom XML Part option.](../media/xml-mapping-pane.png)](../media/xml-mapping-pane.png#lightbox)

1.  On the **XML Mapping** pane, right-click the fields to add them to the document. Then, select **Plain Text** or **Picture** under the **Insert Content Control** menu.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Microsoft Word. Focus is on the Plain Text and Picture options under the Insert Content Control menu in the XML Mapping pane.](../media/insert-content-control.png)](../media/insert-content-control.png#lightbox)

1.  Select, position, and format the fields within the document. A document might resemble the following screenshot.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Word template with header and labels added before and after the multiple data fields.](../media/template.png)](../media/template.png#lightbox)

1.  When the template is ready to be used in the application, upload the saved version of the file. In the same model-driven app and view that you used in a previous step, select a specific record. From the **Word Templates** dropdown menu, select **Upload Template**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of a sample model-driven app, displaying a list of active accounts and the first record selected. Focus is on the Upload Template option of the Word Templates dropdown menu.](../media/upload-template.png)](../media/upload-template.png#lightbox)

1.  In the form, select **Choose File** for the newly created template. Select **Upload** to proceed.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Select file to upload as a template form. Focus is on the Choose File and Upload options.](../media/upload.png)](../media/upload.png#lightbox)

1.  The template will be available to use for any selected record of the table that it uses as a data source. To generate a new document for a record, select the template in the **Personal Word Templates** section of the **Word Templates** dropdown menu.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the uploaded template option that's available in the Personal Word Templates section of the Word Templates dropdown menu.](../media/personal-word-templates.png)](../media/personal-word-templates.png#lightbox)

The generated document that's uploaded to your local computer is based on the template but with the information from the selected record. The following screenshot shows an example of a generated document.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Microsoft Word document that's generated from the template with header, labels, data from the selected record, and formatting applied.](../media/generated-document.png)](../media/generated-document.png#lightbox)

## Next steps

Now, you've learned how to create a Word template that uses Dataverse as a data source to generate standardized documents. Next, you'll learn how to create a work order template.
