The Power Pages site needs a way for the suppliers to navigate to their order details. To help meet the requirement, you create a list.

1. Create a new webpage named **Machine Orders** that uses the blank layout, and make sure that the **Add page to main navigation** checkbox is selected.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Add page to main navigation checkbox selected.](../media/add-page-main-navigation.png)](../media/add-page-main-navigation.png#lightbox)

1. Within the prompt to **Choose a component to add to this section**, select **Text**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Text component being added in with the component highlighted.](../media/add-text.png)](../media/add-text.png#lightbox)

1. Enter **Machine Orders** in the text box and then change **Paragraph** to **Heading 1**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Machine Orders entered in the textbox and Paragraph changed to Heading 1.](../media/heading.png)](../media/heading.png#lightbox)

1. Select the plus (**+**) icon beneath the heading you created and select **List** from the options.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the component options, with the list option highlighted.](../media/add-list.png)](../media/add-list.png#lightbox)

1. In the **Set up** tab, select the **Machine Order** table, set the data view to **Active Machine Orders**, and then name the list **Active Machine Orders**. You can select multiple views, but you only use one for this lab.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Set up tab with details filled in.](../media/set-up-details.png)](../media/set-up-details.png#lightbox)

1. Select **Actions** and then scroll down to **Row actions**.

1. Turn on the **Edit record** toggle. Set the **Target type** to **Webpage**, the **Webpage** to **Machine Order Details**, and then change the **Display label** to **Update**. Select **Done**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the list details filled in.](../media/list-details.png)](../media/list-details.png#lightbox)

## Bug workaround

For this scenario, a bug was found in websites that use the enhanced data model, and the Edit record configuration wasn't saved from the design studio. To fix this bug, follow these steps:

> [!NOTE]
> If you are not using the enhanced data model, skip to **Step 4** of this lab.

1. In the **List settings** window, select **More options** and then select **Open the Portal Management App**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the More options view.](../media/more-options.png)](../media/more-options.png#lightbox)

   The Power Pages Management app opens, where you can edit the website configuration data directly.

1. Select the **Options** tab and then scroll down to the **Grid Configuration** section. In the **Item Actions** area, select **Edit** and then fill in the following values:

   **Target Type** - Basic Form

   **Basic Form** - Supplier Form

   **Button Label** - Update

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Options tab, showing information added in the Edit section.](../media/options.png)](../media/options.png#lightbox)

1. Select **Save & Close**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the save and close option in the portal management app.](../media/portal-manage-save.png)](../media/portal-manage-save.png#lightbox)

1. Return to the design studio, and then select **Sync**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the sync button at the top right of the power page editor screen.](../media/sync.png)](../media/sync.png#lightbox)

    The preview in the studio should resemble the following screenshot.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the preview of Machine orders.](../media/preview.png)](../media/preview.png#lightbox)

   > [!NOTE]
   > If you did not need to perform the bug workaround, continue from this step.

1. In the upper-right corner of the screen, select **Preview > Desktop**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the desktop preview.](../media/desktop.png)](../media/desktop.png#lightbox)

1. The website loads in a new tab. Within the list on the page, an error message appears, stating that you don't have permission to view the records. The next task will address this issue.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the permissions message stating that you don't have permissions to view the records.](../media/permissions.png)](../media/permissions.png#lightbox)
