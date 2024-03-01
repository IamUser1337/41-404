Now that you created the table to store machine order requests, you connect your Machine Ordering canvas app to this table and then add a form to submit machine approval requests.

> [!NOTE]
> To complete the exercises, you'll need to use a few
> files. Download the [App in a Day files](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/raw/master/in-a-day/AIAD/AppinADayStudentFiles.zip)
> for use in this module. The file folders that are in
> this download include:
>
> - **Completed modules with instructions** - Package files to import the completed exercise steps.
> - **Machine-Order-Data.xlsx** - File used in the exercises.

## Task - Add a Microsoft Dataverse table as a data source to the app

Open the Machine Ordering app. Make sure that you're opening the version of the app that's in the newly created environment that has the Microsoft Dataverse database instance.

1. Within **Power Apps**, select **Solutions** from the navigation pane to the left of the screen, and then open the **Contoso Coffee** solution.

1. Select **Apps** from the Objects pane to the left of the screen, choose **Machine Ordering App**, and then select **Edit** from the tool bar.

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing the Edit application button.](../media/edit.svg)](../media/edit.svg#lightbox)

1. Select the **Data** icon from the navigation pane to display the current sources. Then, select the **+ Add data** dropdown.

1. Select **Machine Orders** from the table list to include it as a data source for your app.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Machine Orders option selected in the Select a data source menu.](../media/data-source.png)

## Task - Create the edit form

Next, you create the edit form by following these steps:

1. Switch to the **Tree view** pane using the icons within the navigation pane, and then select the **Main Screen**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Main Screen option highlighted in Tree view.](../media/tree-view.png)

1. Select a few machines. Press and hold the **Alt** key, which allows you to select the compare checkbox.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of a few machines selected on the Machine Ordering app.](../media/compare.png)](../media/compare.png#lightbox)

1. Select **Compare Screen** from the **Tree view**. The selected machines should now display.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the compare screen selected and the selected machines displayed.](../media/comparison.png)](../media/comparison.png#lightbox)

   > [!NOTE]
   > If the navigation arrow button appears within the **galCompareList** on the **Compare Screen**, select the **galCompareList** from the Tree View pane, and set the **Width** value of the gallery to `845`.

1. Select the **+ Insert** dropdown from the tool bar, search for **edit**, and then select **Edit form**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing the Edit form button in the Insert dropdown menu.](../media/edit-form.png)](../media/edit-form.png#lightbox)

1. In the data pane to the right of the screen, select the **Data source** dropdown menu.

1. Select the **Machine Orders** table as the data source.

   > [!div class="mx-imgBorder"]
   > ![Screenshot showing the Machine Orders table.](../media/machine-orders.png)

1. Select **Edit fields** next to `Fields` in the properties panel.

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing the Edit fields option.](../media/edit-fields.png)](../media/edit-fields.png#lightbox)

1. Add, remove, and arrange fields as ordered in the following list. You can add the fields by using the plus (**+**) sign, and you can reorder them by dragging the field to the desired placement.

    1. Machine Name

    1. Price

    1. Approver

    1. Comments

    1. Requested By

    1. Request Date

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the selected fields.](../media/fields.png)

1. Close the **Fields** pane.

1. Rename the form as `frmMachineOrder`.

   > [!div class="mx-imgBorder"]
   > ![Screenshot showing the form being named as Machine Order Form.](../media/machine-order-form.png)

1. Rename the `datacards` for the form according to this screenshot.

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing the renamed data cards for the form.](../media/form-card-renames.png)](../media/form-card-renames.png#lightbox)

1. Select the **frmMachineOrder**.

1. Set the **X** value to `900`.

1. Set the **Y** value to `60`.

1. Set the **Width** value of the **frmMachineOrder** to `455`.

1. Set the **Height** value of the form to `650`.

1. Within the properties pane to the right of the screen, change the **Snap to columns** value to **1**. This setting modifies the layout of the edit form to be a single column.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Columns field being changed to 1 under the Snap to columns section.](../media/columns.png)

   The form should now resemble the following image.

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing the form.](../media/form.png)](../media/form.png#lightbox)

   > [!NOTE]
   > You can always select controls, such as the **Form1** control, from the tree view on the left to make sure that you're selecting the correct control. To move it, make sure that you select the form and not a control within the form.
   >
   > For more information, see [Understand data-form layout for canvas apps](https://powerapps.microsoft.com/tutorials/working-with-form-layout/?azure-portal=true).

1. To create a new instance of the form when the screen is loaded, select **Compare Screen** in left tree view pane.

1. Select the **OnVisible** property of the screen and then enter the following formula:

    `NewForm(frmMachineOrder)`.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the OnVisible property selected.](../media/on-visible.png)](../media/on-visible.png#lightbox)

## Task - Set up the title column

In the next few steps, you set up each form field.

Your first task is to set up the title to display the machine type and machine name for the selected machine. For example, if the user selects the Smart Brew 300 coffee makers, you want the machine order to have the title of "At home coffee makers - Smart Brew 300."

1. Expand the **crdMachineName** data card under the **frmMachineOrderForm** in the tree view.

   > [!div class="mx-imgBorder"]
   > ![Screenshot highlighting the expand button of the machine name datacard.](../media/machine-name.png)

   The default card contains a few controls:

   - **StarVisible1** - A label control that has an asterisk (\*\) and has its **Visible** property set to **true** or **false**, depending on whether the field is required or not. Because the **Title** field was set as **Required** when you set up the table, its **Required** property is set to **true**.

   - **ErrorMessage1** - A label that is directly below the main data entry field that displays error messages.

   - **DataCardValue1** - The text input control where you can enter the title. For this scenario, you set the title based on the selected machine.

   - **DataCardKey1** - The label that displays the title of the field.

   > [!NOTE]
   > Continue to rename all controls following the proper naming conventions. Screenshots following from here will have naming conventions applied that may be somewhat different from what you decided.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with a box around the controls of the data card.](../media/data-card.png)

1. Select **crdMachineName** in the tree view. Then, select the **Advanced** tab from the pane to the right.

1. Select **Unlock** so that you can customize the card.

   > [!div class="mx-imgBorder"]
   > ![Screenshot highlighting the lock icon.](../media/lock.png)

   > [!NOTE]
   > For the next few steps, you'll use the Advanced pane to customize control properties within the form. You can perform the same customizations by using the property dropdown menu and formula bar in the upper left of the studio.

1. Go to the **Data** section and set the **Default** property to:

   `'galCompareList'.Selected.'Machine Type' & " - " & 'galCompareList'.Selected.'Machine Name'`

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the default property set to the preceding value.](../media/data-default.png)

1. Change the **DisplayMode** to `DisplayMode.View`. This setting prevents users from changing the value within the text box.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the DisplayMode field changed.](../media/display-mode.png)

## Task - Set up the Price field

In this task, you set the price to the price of the item and then make it read-only.

1. Expand **crdPrice** for the Compare Screen within the Tree View pane.

   > [!div class="mx-imgBorder"]
   > ![Screenshot highlighting the expand button for Price Datacard.](../media/price-data.png)

1. Select the **dcvPrice**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with a box around the Data Card Value 3 option.](../media/data-card-value.png)

1. Select the **Advanced** tab within the properties pane and then select **Unlock**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Price Data Card Value Advanced tab and the lock icon.](../media/data-advanced.png)

1. Change the **Default** property in the **Data** section to:

   `Text('galCompareList'.Selected.Price,"$##,###.00")`

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the default property changed in the Data section.](../media/default-changed.png)

1. Select the **Price Data Card** within the Tree View pane and change the **DisplayMode** property value to `DisplayMode.View` using the formula bar.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Display Mode property changed to View.](../media/display-mode-changed.png)

## Task - Set up the Approval field

In this task, you set the **default** value for the approver to be the email address of the signed-in user's manager.

You use Microsoft Graph to retrieve the manager's email. For more information, see [Office 365 Users Connection Provider](/connectors/office365users/?azure-portal=true).

1. Select the **Data** icon from the navigation menu. Select the **+ Add data** dropdown and then expand **Connectors**. Select **Office 365 Users**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot highlighting the Office 365 Users option under Connectors.](../media/connectors.png)

1. When prompted, select **Connect**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with an arrow pointing to the Connect button on the prompt screen.](../media/connect.png)

1. Select the **Approver Data Card Value** renamed **dcvApprover** within the Compare Screen from the Tree view pane.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with a box around Approver Data Card under the Tree view.](../media/approver.png)

1. Switch to the **Advanced** tab within the pane to the right of the screen, and select **Unlock**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with an arrow pointing to the lock icon, which will unlock when you select it.](../media/unlock.png)

1. Under the Data section, set the **Default** property value to:

   `User().Email`

   This expression uses your user's email so that you don't accidentally email your manager to approve your testing.

   In a real application, or if you wanted to try the expression to use your manager's email, it would be:

   `Office365Users.Manager(User().Email).Mail`

   The expression would make an API call at runtime to get the manager's email address of the signed-in user.

   If you try it and get an error when calling the **Office365Users.Manager()** function, it might be because a manager isn't set up in the system for the signed-in Office 365 user. In that case, you can return to **User().Email**.

1. **Save** your work and return to continue editing the app.

The Office 365 User connector has access to many other valuable types of information. For more information, see [Office 365 Users Connector](/connectors/office365users/?azure-portal=true).

## Task - Set up the Comments field

Your next task is to set up the **Comments** field by following these steps:

1. Expand the **Comments** Data Card and select the **DataCardValue** renamed **dcvComments** within the Tree View pane.

1. Under the Properties tab of the pane to the right of the screen, set the **Hint text** property to `Enter justification`.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Hint text field changed to Enter justification.](../media/justification.png)

## Task - Set up the Requested By field

Next, you set the **Requested By** field to be the current signed-in user's email, and then you disable the control so that the user can't change this value.

1. Expand the **Requested By** Data card renamed **crdRequestedBy** from the **frmMachineOrder** within the Tree view pane.

1. Select the **DataCardValue** renamed to **dcvRequestedBy**.

1. Switch to the **Advanced** tab within the pane to the right of the screen and **Unlock** the card.

1. Change the **DisplayMode** property to `DisplayMode.View`.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Display Mode property changed.](../media/view.png)

1. Under the Data section within the pane, set the **Default** value to `User().Email`.

   The email of the currently signed-in user should display.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the currently signed-in user.](../media/user.png)

## Task - Set up the Request Date field

In this task, you set the **Request Date** field to be today's date.

1. Expand the **crdRequestDate** within the Machine Order Form from the Tree View pane.

1. Select the **DateValue** card renamed **dteRequestDate**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with a box around the Date Value 1 card.](../media/date.png)

1. Switch to the **Advanced** pane to the right of the screen and **Unlock** the card.

1. Change the **DefaultDate** property to `Today()`.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Default Date property changed.](../media/default-date.png)

   The date in the calendar control changes to today's date.

   Now, you hide the **crdRequestDate** card. You don't need to show this field to the user. Because you include it as part of the form, the field is updated as part of the form submit.

1. Select the **crdRequestDate** card from the Machine Order Form within the Tree View pane.

1. Navigate to the **Properties** pane and set the **Visible** toggle to **Off**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Visible toggle changed to Off.](../media/visible.png)

## Task - Add a button to submit the form

To add a button to submit the form, follow these steps:

1. Select the **Main Screen** within the Tree View pane.

1. Copy (**Ctrl+C**) the **Compare** button from the first screen, which has the correct color values.

   > [!div class="mx-imgBorder"]
   > ![Screenshot showing the Compare items button.](../media/compare-items.png)

1. Return to the **Compare Screen** and paste (**Ctrl+V**) the button.

   > [!div class="mx-imgBorder"]
   > ![Screenshot showing the Compare items button again.](../media/paste.png)

1. Make sure that the button is larger and positioned correctly. You can resize to **260 x 40** by using the **Properties** pane on the right. You might also need to reposition the button on the screen.

   *Notice in the button in this image is positioned to 1090 (X value) and 720 (Y value).*

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the resize button settings.](../media/size.png)

1. Within the Tree view pane, rename the button to `btnSubmit`.

1. Using the formula bar, set the button's **Text** property to `"Submit machine request"`.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the button's text property changed.](../media/submit.png)

1. The button should be enabled only if a machine is selected. To do so, change the button's **DisplayMode** property to:

   `If(!IsBlank('galCompareList'.Selected), DisplayMode.Edit, DisplayMode.Disabled)`

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the button's display mode property changed.](../media/button-display.png)](../media/button-display.png#lightbox)

   > [!NOTE]
   > You might notice the exclamation mark (**!**) in the formula `!IsBlank()`. Normally, if you only have `IsBlank()`, the check is for **blank** only. Adding the exclamation mark (**!**) in front of the formula will change it to check if it's **not blank**.

1. Set up what you want to happen when the button is selected by setting the **OnSelect** property to the following:

   `SubmitForm('frmMachineOrder')`

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the On Select property.](../media/on-select.png)

   When the button is selected, the form data is submitted to Microsoft Dataverse.

1. Save your work and then return to continue editing the app.

## Task - Test the form

Your next task is to test the form.

1. Select the **Main Screen** within the Tree view pane. Then, select the **Preview the app** button.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with a box around the play icon.](../media/play.png)

1. Select a few machines to compare and then select **Compare**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot highlighting the Compare items button.](../media/compare-three.png)](../media/compare-three.png#lightbox)

1. Select one of the machines.

   The **Machine Name**, **Price**, **Approver**, and **Requested By** fields are filled in already.

1. Add some **Comments**, such as: `This machine will satisfy our needs.`

1. Select **Submit machine request**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing a machine selected and the Submit machine request button.](../media/submit-machine.png)](../media/submit-machine.png#lightbox)

   The button should turn disabled (gray) for a few seconds while it's submitting the request. If it doesn't, an error probably occurred. Select the **X** in the upper-right corner to return to the design mode.

   If an error occurs, a yellow error icon displays next to the **Submit** button. You can hover your mouse cursor over the icon to check the error.

1. Exit the preview mode by selecting the **X** in the upper-right corner.

1. Select the **Publish** button located in the top right hand corner of the page.

1. Select **Publish this version** and then wait for the application to be published.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with an arrow pointing to the Publish this version button.](../media/publish.png)

## Task - Verify that a new item was added to the Machine Order table

Your next task is to verify that a new item was added to the Machine Order table.

1. Open a browser window and then go to [Make Power Apps](https://make.powerapps.com/?azure-portal=true).

1. Select **Tables** from the navigation pane to the left for the screen.

1. Select the **Machine Order** table.

   > [!div class="mx-imgBorder"]
   > [![Screenshot with an arrow pointing to the Machine Order table under the Tables section.](../media/machine-order.svg)](../media/machine-order.svg#lightbox)

   A newly added row with your machine order details should display. It might take a few seconds to load.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the newly added row with your machine order details.](../media/details.svg)](../media/details.svg#lightbox)

## Optional task - Navigate to the confirmation screen after the form submission is successful

This step is optional. If you're short on time, you can skip this step and continue to the next module.

After the form is successfully submitted, it's a good idea to show a confirmation screen and allow the user to return to the main screen.

1. Open a browser window and then go to [Make Power Apps](https://make.powerapps.com/?azure-portal=true). Sign in if needed.

1. Within the navigation pane to the left of the screen, select **Apps**.

1. Then, select **Machine Ordering App** and then choose **Edit** from the tool bar at top of the page.

1. Within the Tree view pane, select the **+ New screen** dropdown, and choose **Blank**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the add New screen button and the Blank option highlighted.](../media/blank.png)

1. Rename the screen to `Submit Success Screen`.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the screen renamed to Submit Success Screen.](../media/submit-success.png)

1. Expand the **Compare Screen** within the Tree view pane.

1. Select **frmMachineOrder**.

1. Set the **OnSuccess** property of the form to the following formula using the formula bar at the top of the screen:

   `Navigate('Submit Success Screen', ScreenTransition.None)`

   > [!div class="mx-imgBorder"]
   > [![Screenshot showing the On Success value of the form.](../media/on-success.png)](../media/on-success.png#lightbox)

1. Copy (**Ctrl+C**) the **Header** from the **Compare Screen**.

1. Go to the **Submit Success Screen** and paste the header.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the header pasted and the top aligned.](../media/header.png)](../media/header.png#lightbox)

1. Using the **+ Insert** dropdown from the tool bar at the top of the screen, add a **Text label** to the middle of the screen. Then, set the **Text** property value to the following:

   `"Your machine request has been successfully submitted. Thank you."`

1. Using the tools at the top of the screen, change the **font size**, **alignment**, and **resize** the label as needed within the canvas. For this example, we changed the font size to `14`, the text alignment to **center**, and resized the visual as shown in this image.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the font size increased, the size increased, and the text centered.](../media/label.png)](../media/label.png#lightbox)

1. Within the Tree view pane, copy the **Submit Button** from the **Compare Screen** and then paste it in the **Submit Success Screen**.

1. Rename the button as `btnSuccess` and change all other control names as necessary.

1. Change the **Text** property value of the **Success Button** to `"OK"` using the formula bar at the top of the screen.

1. Change the **Display Mode** of the **Success Button** to `DisplayMode.Edit`.

1. Reposition the button to the middle of the screen.

   When pressed, the button should remove items from the **CompareList** collection and navigate to the main screen.

1. Set the **OnSelect** property of the button to:

   `Clear(CompareList);Navigate('Main Screen',ScreenTransition.None)`

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the On Select property of the button selected.](../media/ok-button.png)](../media/ok-button.png#lightbox)

   > [!NOTE]
   > The semicolon (**;**) is used as a separator when multiple functions are called one after the other. If you're in a locale where the semicolon is used as a comma separator, then use a double semicolon (**;;**).

1. Select the **+ Insert** dropdown at the top of the screen, searching for `display`, and then choose **Display form**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Insert dropdown menu and the Display form option selected.](../media/display.png)

1. Within the **Properties** pane to the right of the screen, set the form's **Data source** to the **Machine Orders** table.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with an arrow pointing to the expand icon and a box around the Machine Orders table.](../media/data-machine.png)

1. Select **2 selected** below the Data source, and select the following fields to display: **Machine Name**, **Price**, **Comments**, **Approver**, **Requested By**, and **Request Date**. Rearrange and remove extra fields.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the Fields menu and the fields to select.](../media/fields-menu.png)

1. Change the **Snap to columns** value to **1**.

1. Change the **Layout** to **Horizontal**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot with a box around the Horizontal layout option.](../media/horizontal.png)

1. Set the form's **Item** property value to the following formula:

   `'frmMachineOrder'.LastSubmit`

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the form's Item property changed.](../media/last.png)

1. Reposition and resize the form until it resembles the following image. The label is first on the screen, centered under the header. Position the view form to be centered under the label. Then, center the **OK** button at the bottom of the page under the view form.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of the resized form. Label is centered under the header. The view form is centered under the label. The okay button is centered under the view form.](../media/resized.png)

1. Save your changes and **Publish**.

1. Select the **Main Screen** and then select **Play**.

1. Select a few machines and then select **Compare**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot with a highlight around the Compare items button.](../media/compare-three.png)](../media/compare-three.png#lightbox)

1. Select one of the machines, provide a comment, and then select **Submit machine request**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the compare screen, highlighting the Comments and Submit machine request boxes"](../media/comment.png)](../media/comment.png#lightbox)

1. Verify that the confirmation screen shows the order details. Select **OK**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot highlighting the okay button at the bottom of the confirmation screen of the order details.](../media/order-details.png)](../media/order-details.png#lightbox)

   The application returns to the main screen and the compare list are cleared.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the cleared compare list on the main screen.](../media/clear.png)](../media/clear.png#lightbox)

1. Close the application.
