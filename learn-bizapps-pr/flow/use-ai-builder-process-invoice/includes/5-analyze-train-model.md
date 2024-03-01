When your collections are complete and all documents are uploaded, select **Next** to prompt Power Automate to analyze your documents to identify their overall structure, detect form fields, and extract values.

> [!div class="mx-imgBorder"]
> ![Screenshot of the next button to start analysis.](../media/next.png)

> [!NOTE]
> The analysis might take a few minutes as Power Automate works in the background.

When the analysis is complete, your documents will appear organized by collection. In the document, you can use the mouse to select and drag the values that you want to capture. After you've made a selection, a pop-up window will appear showing the fields that you added previously. Select the **Bill to** field, as shown in the following screenshot. A green checkmark will appear on the right panel as you locate and identify the various fields.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Show detected words dialog box with fields being selected.](../media/9-train-model.png)](../media/9-train-model.png#lightbox)

After you've identified all necessary fields, you can select the next document. Completed documents will be highlighted in blue with a white checkmark. The model might pick up on some fields automatically, and if this occurs, you should look at each document to ensure that each field is correct. You can view which field is related to which value by hovering over the field name. If a field is incorrect or not in the document, select the ellipses (**...**) by the field name to reveal more actions.

> [!div class="mx-imgBorder"]
> [![Screenshot of invoice number details.](../media/invoice-number.png)](../media/invoice-number.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of a document fields.](../media/fields.png)](../media/fields.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of a document's fields with the ellipsis button next to one selected to show field options.](../media/10-more-options.png)](../media/10-more-options.png#lightbox)

If you're having difficulty selecting a value, you can use the magnifying glasses in the upper portion of the screen to adjust the zoom.

When you've finished identifying the values for every field on every document, select **Next**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Show detected words dialog box with the Next button highlighted.](../media/11-next.png)](../media/11-next.png#lightbox)

Select **Train** to start training the model. This process might take a few minutes.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Model summary dialog box with the Train button highlighted.](../media/12-train.png)](../media/12-train.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of the your model is training message.](../media/progress-message.png)](../media/progress-message.png#lightbox)

When the process is done, select **Go to models** and select **Publish** on the following screen.

> [!div class="mx-imgBorder"]
> ![Screenshot of the go to models button.](../media/models.png)

> [!div class="mx-imgBorder"]
> [![Screenshot of the Models > Enter invoice information AI model dialog box with the Publish button highlighted.](../media/13-publish.png)](../media/13-publish.png#lightbox)

Once you see **Use model**, you can now use the model in Microsoft Power Apps or Power Automate.
