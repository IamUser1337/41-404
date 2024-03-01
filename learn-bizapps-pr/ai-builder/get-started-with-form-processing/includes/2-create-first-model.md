The following procedures show you how to create a Document processing model in AI Builder. This guided experience walks through each step of the model creation process. You can save your work and return at any time. Progress will be saved automatically when you move between steps.

## Sign in to AI Builder

Follow these steps to sign in to AI Builder:

1. Go to [Power Automate](https://make.powerautomate.com/) and sign in with your organizational account.
1. In the left pane, select AI Hub.
1. Select Document processing.
1. If you want to create your model by using your own documents, make sure that you have at least five examples that use the same layout. Otherwise, you can use sample data we'll be using in this guided experience. You can download the sample data in [English version](https://go.microsoft.com/fwlink/?linkid=2128080) or in [Japanese version](https://go.microsoft.com/fwlink/?linkid=2186887)
1. Select create custom model.

## Choose document type

Select the type of document you want to build an AI model to automate data extraction. There are three options:

- **Structured and semi-structured documents**. In structured and semi-structured documents, the fields, tables, checkboxes, and other items for a given layout are in similar places. Examples of structured and semi-structured documents include invoices, purchase orders, delivery orders, and tax documents.

- **Unstructured and free-form documents**. In unstructured documents, there's no set structure, usually with a varying number of paragraphs. Examples of unstructured documents are contracts, statements of work, letters, etc.

- **Invoices**. Invoice documents are standard account payable forms. This model type comes with standards fields and you can teach this model to extract additional custom data or update the standard data. Examples of such documents include invoices and purchase orders.

![Screenshot of the AI Builder "Choose document type" page where to choose between structured or unstructured documents or invoices.](../media/select-type-documents.png)

## Choose information to extract

In this step, define the fields and tables you want to teach your model how to extract.

The provided sample data in [English version](https://go.microsoft.com/fwlink/?linkid=2128080) or in [Japanese version](https://go.microsoft.com/fwlink/?linkid=2186887) are invoices from two different providers. Define the following fields to extract:

- Invoice number
- Customer ID
- Total amount
- Due date

1. Select **+ Add** and then select **Text field**.

    ![Screenshot of the Power Automate "Choose information to extract" page adding four fields on the Text Field tab.](../media/select-add-text-field.png)

2. Enter the Text field name **Invoice Number** and select **Done**, repeat this step for **Customer ID**.

1. Select **+ Add** and then select **Number field (preview)**.

    ![Screenshot of Number field.](../media/select-add-number-field.png)

2. Enter the Number field name **Total amount** and select **Done**.

3. Select **+ Add** and then select **Date field (preview)**.

    ![Screenshot of the Power Automate "Choose information to extract" page Date field is selected.](../media/select-add-date-field.png)

4. Enter the Date field name **Due Date** and select **Done**.

    The model will learn how to extract these fields from the document.

    ![Screenshot of the Power Automate "Choose information to extract" page about four fields name to be extracted from the document.](../media/fields-extracted.png)

    We also want to extract the description and total amount for each line item present on the invoice. Define a table named **Items** and with the columns **Description** and **Item total**.

7. Select **Add** + and then **Add Table**, and then **Next**.

    ![Screenshot of the Power Automate "Choose information to extract" page adding a single Page Table item.](../media/select-add-table.png)

8. Define as table name **Items** and define the columns **Description** and **Item total**. 
9. Select **Column1** and then rename **Column1 by Description**.
10. Select **+ Add column**, enter the column name **Item total**.

    ![Screenshot of the Power Automate "Choose information to extract" page defining a table name items and renaming the column name.](../media/define-table-name-items.png)

    ![Screenshot of the Single Page Table.](../media/single-page-table.png)

## Define collections and upload documents

A collection is a group of documents that share the same layout. Create as many collections as documents with different layout that you want your model to process. Since we have two invoice providers, and each invoice provider uses a different invoice template, we define two collections.

1. Select **New Collection** and change the name of the first collection to **Adatum**.  

    ![Screenshot of the Power Automate "Add collections of documents" page selecting new collection.](../media/select-new-collection.png)

2. Name the first collection **Adatum** and the second collection **Contoso**.

    ![Screenshot of the Power Automate "Add collections of documents" page selecting a new collection and changing its name.](../media/change-collection-name.png)

    ![Screenshot of the Power Automate "Add collections of documents" page selecting a second collection and changing its name.](../media/naming-two-collection-names.png)

    Now that we've created our two collections, we'll need to upload at least five samples for each collection.

    For the collection named **Adatum**, upload the five documents from the **AI Builder Document processing Sample Data/Adatum/Train** folder.

3. Select the **+** icon in each collection.

    ![Screenshot of the Power Automate "Add collections of documents" page selecting a collection Adatum.](../media/select-plus-adatum.png)

4. Select **Add documents**, and select **My device** as a data source.

    ![Screenshot of the Power Automate "Add collections of documents" page selecting Add documments.](../media/select-adatum-document.png)

    ![Screenshot of the Power Automate "Add collections of documents", "Add documents" page selecting my device as a data source.](../media/adatum-my-device.png)

5. Select five documents from your local device and select upload documents. Those five uploaded documents will be used to train your model.

    ![Screenshot of Power Automate "Add collections of documents" page uploading five documents from a data source to be used to train a model.](../media/adatum-upload-five-documents.png)

    ![Screenshot of Power Automate "Add collections of documents" page showing a document in a collection.](../media/adatum-five-documents.png)

    Once the five documents are uploaded to your collection Adatum, you can repeat these steps above for the collection Contoso.

6. For the collection names **Contoso**, upload the five documents you'll find on the **AI Builder Document processing Sample Data/Contoso/Train** folder.

7. Once you've uploaded the sample documents to each collection, select **Next** to continue.

## Tag documents

Now is the time to teach your AI model how to extract the fields and tables you've defined. Begin by tagging the sample documents you've uploaded.

To start the tagging process, select a collection on the right panel.


### Tag fields

Let’s start by tagging our defined fields **Invoice number**, **Due date**, **Total amount**, and **Customer ID**. To tag a field, draw a rectangle around the field on the document and select the field name it corresponds to.

![Screenshot of the Power Automate "Tag documents" page drawing a rectangle around a field.](../media/tag-field-invoice-number.png)

![Screenshot of the Power Automate "Tag documents" page selecting a field name.](../media/invoice-number-selected-right-pane.png)

You can resize to adjust your selection at any time.

When you hover over different words in your documents, light blue boxes appear. The boxes indicate that you can draw a rectangle around those words to select a field.

![Screenshot of address with number selected.](../media/forms-address.png)

### Field or table not in document

Not all defined fields and tables need to necessarily be in all documents. If you've started by tagging the Contoso collection, you'll see that the field Customer ID isn't present. Tell the AI model that fields aren't present by going to the field or table on the right panel and selecting **‘Not available in the document’** in the three dotted menu.

![Screenshot of the Power Automate Tag documents page selecting Not available in the document in the three dotted menu.](../media/customer-id-not-available-document.png)

### Tag tables

To tag a table: 

1.	Draw a rectangle around the table in the document you're interested in, and then select the table name that it corresponds to.

    ![Screenshot of the Power Automate "Tag documents" page drawing a rectangle around a table.](../media/draw-rectangle.png)

    The content of the panel on the right will change.

    ![Screenshot of the Power Automate "Tag documents" page showing the right panel that have changed.](../media/content-panel-right-change.png)

2.	Draw rows by left clicking between row separators.

    ![Screenshot of the Power Automate "Tag documents" page drawing rows by left clicking between row separators.](../media/draw-rows-left-click.png)

3.	Draw columns by pressing Ctrl + left-click (or ⌘  left-click on macOS).

    ![Screenshot of the Power Automate "Tag documents" page drawing columns by pressing ctrl + left-click.](../media/draw-columns.png)

4.	Once the rows and columns have been set, assign the headers to extract by selecting the header column and mapping it to the desired one.

    ![Screenshot of the Power Automate "Tag documents" page assigning and selecting header on the first column.](../media/select-description-header.png)

    ![Screenshot of the Power Automate "Tag documents" page assigning and selecting header on the second column.](../media/select-amount-header.png)

5.	A preview of how the table will be extracted appears on the panel on the right.

    ![Screenshot of the Power Automate "Tag documents" page showing a preview of how the table will be extracted.](../media/preview-table-extracted.png)

6.	If the header of the table has been tagged, select Ignore first row so the header of the table isn't extracted as the table content.

    ![Screenshot of the Power Automate "Tag documents" page ignoring the first row of the table that has been tagged.](../media/ignore-first-row.png)

    ![Screenshot of the Power Automate "Tag documents" page with the first row of the header ignored.](../media/ignore-first-row-result.png)


### Tag all documents

Once you have finished tagging one document, move to the next one to tag by clicking the navigation arrows bellow the document preview on the top right.

Once you have finished tagging one collection, navigate back to the collection list to tag the second collection.

![Screenshot of the Power Automate "Tag documents" navigating back to the collection list.](../media/tag-table-05.jpg)

## Summary and train

After you've tagged all documents across all collections, follow these steps:

1. Select **Next**.
2. Review the summary of your model's details. If everything looks acceptable, select **Train**.

## Next steps

Now that you've created a Document processing model in AI Builder, you'll learn how to test your model and use it in Power Apps and Power Automate.

