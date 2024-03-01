Learn how to use your Object detection model in Power Apps.

### Quick test

After your model has completed training, you can view important details about your newly trained model on a details page.

![Screenshot of your newly trained model details page.](../media/use-your-model.png)

To see your model in action, select **Quick test**.

Drag and drop or upload an image from your device to test. From the provides sample data, use the files from the Test folders that we didn’t use for training (either from **AI Builder Document processing Sample Data\Adatum\Test** or **AI Builder Document processing Sample Data\Contoso\Test**).

You will now be able to view the detected fields that you chose and the associated confidence scores for retrieving the individual fields compared to the trained model.


### Publish your model

Your model can't be used until you publish it. If you're satisfied with your model, select **Publish** to make it available for use.

### Use your model in Power Automate

Now that your model is published, you can use your Object detection model in a canvas app. A special component is available for you to add that analyzes any image and detects objects based on your trained object detection model.

1. Select **Use model**.

2. Select **Build intelligent automations** and select one of the triggers proposed. For this module we will use the **Microsoft 365 Outlook work account**.

3. Make sure that you are signed into the flow and then select **Continue** to confirm the creation of the flow.

   ![Screenshot of triggers that your flow will connect to.](../media/use-your-model-02.jpg)
 

   The flow has already been configured to run when you receive an email with an attachment and the email subject is: AI Builder. Let's see it in action!

   [ ![Screenshot of sample flow illustrating how to use your newly trained model.](../media/use-your-model-03.jpg) ](../media/use-your-model-03.jpg)

4. Select **Save** on the top right to test the flow.
5. Select **Test**.
6. Select **Manually** and then select **Test**.
7. Now send yourself an email with the subject **AI Builder** and attach the document you used for quick test previously.
8. After a few seconds, you will see the flow running. The flow will extract the data from the attachment and send you back an email with the results.

Congratulations! You’ve built an intelligent automation flow. You can then customize the flow to your needs to perform any other action you may want.

### Use your model in Power Apps

Now that your model is published, you can use your Document processing model in a canvas app. A special component is available for you to add that analyzes any image and extracts the text based on your trained Document processing mode.

   [ ![Screenshot of your Document processing model published in Power Apps.](../media/use-your-model-powerapps.png) ](../media/use-your-model-powerapps-expanded.png)
 
1. Select **Use model**.

2. Select **Build intelligent apps** to begin the canvas app creation experience.

3. Within your canvas app, a Form processor component is automatically added and linked to your published Document processing model.

   Going forward, you can select **+ > AI Builder** from the left pane to view the list of AI Builder components and then select **Form processor** to add a Form processor component. Make sure that you select the correct model. Only published models will appear in the drop-down list.

      [ ![Screenshot of published models appearing in the drop-down list in Power Apps.](../media/select-ai-models.png) ](../media/select-ai-models.png)


4. Select **Insert** and then add a **Label** component.

5. To bind the **Label** component to one of the form fields, select the **Fields** property on the formula bar. This selection retrieves the details of the extracted form fields.

6. To choose a field to display, select one of the names from the **Fields** property. If you want to select table content, select one of the names from the **Tables** property.

   ![Screenshot of a field name in the Fields property in Power Apps.](../media/formprocessor-formula.png)

7. Select **Play** on the upper right of the Power Apps studio to preview the app.
Select **Analyze** and then select the image that you used to quick test previously.

   A preview of your document shows the detected fields and the values that were detected for the fields that you chose.
