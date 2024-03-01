After having initialized a model, your first step toward customization is to choose the information to extract, called fields. Later, you can use fields in flows inside of actions to contribute to your RPA. In this scenario, you'll use the fields to populate the input variables for a desktop flow.

First, select the type of document you're working with. In our case, they're **Structured** documents so select that option.

> [!div class="mx-imgBorder"]
> [![Screenshot of the document type.](../media/document-type.png)](../media/document-type.png#lightbox)

To add fields, select the drop-down arrow next to **+ Add** and select **Field**, enter the field name in the provided text box and select **Done**. The following screenshot shows the **Bill to** field. Follow the same process for **Contact**, **Date**, and **Total**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Choose information to extract dialog box.](../media/4-add-fields.png)](../media/4-add-fields.png#lightbox)

> [!div class="mx-imgBorder"]
> ![Screenshot of the add field name with done button.](../media/field-done.png)

Select **Next** to continue.

> [!div class="mx-imgBorder"]
> ![Screenshot of the added fields listed.](../media/fields-added.png)

Next, you'll add collections of documents for your model to study. Collections allow you to group documents with different layouts, such as when you have customers or organizers who have different layouts for invoicing or other repeated documentation. The same model can process as many as 100 distinct collections. 

> [!div class="mx-imgBorder"]
> ![Screenshot of the new collection button.](../media/new-collection.png)

To add a new collection, select **New collection**. To rename the newly created collection, double-click the automated collection name (in this case, **Collection 1**).

> [!div class="mx-imgBorder"]
> [![Screenshot of the Add collections of documents dialog box.](../media/5-new-collection.png)](../media/5-new-collection.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of the add documents button.](../media/add-documents.png)](../media/add-documents.png#lightbox)

For this example, the collection has been renamed to **Contoso** and five invoice documents have been added, as shown in the following image. To add documents, select the plus sign (**+**), select **Add documents**, and then select your desired data source.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Automate with Contoso selected and the Add documents button highlighted.](../media/6-select-data-source.png)](../media/6-select-data-source.png#lightbox)

Select the documents that you want. An upload screen will appear, showing the documents that you've chosen. Select **Upload documents**, and a screen will display the status of each document. When the upload is complete, select **Close**.

> [!NOTE]
> You may use the [sample invoices](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/raw/master/power-automate-desktop/SampleInvoices.zip) for this exercise. They differ slightly from the screenshots.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Upload documents dialog box.](../media/upload-documents.png)](../media/upload-documents.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of the Upload complete.](../media/7-upload-complete.png)](../media/7-upload-complete.png#lightbox)

[Sample documents](/ai-builder/form-processing-sample-data/?azure-portal=true) are available.

> [!NOTE]
> Now that you've completed your collection and have added your fields, you're ready to analyze and train your model. Simply click **Next**.

> [!div class="mx-imgBorder"]
> ![Screenshot of the upload with next button.](../media/upload-next.png)
