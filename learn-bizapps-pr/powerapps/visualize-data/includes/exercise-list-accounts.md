In this exercise, you'll apply your knowledge to create a view for accounts that you manage. Additionally, you'll ensure that the view shows the records as sorted from the highest annual revenue to the lowest.

Go to a Dataverse environment where you can modify the tables, such as dedicated training or development environment. Then, follow these steps to complete the exercise:

1. Sign in to [Power Apps portals](https://make.powerapps.com/?azure-portal=true).

1. In the left pane, expand **Dataverse** and then select **Tables**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Power Apps portals showing the Dataverse option expanded and Tables selected.](../media/dataverse-tables.png)

1. In the list of tables, select **Account**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the list of Tables in Power Apps portals, showing the Account table selected.](../media/account-table-name.png)](../media/account-table-name.png#lightbox)

1. In Power Apps portals, for the Account table, select **Views**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Account table designer, showing the Views option.](../media/views.png)](../media/views.png#lightbox)

1. Select the **New view** option.

    > [!div class="mx-imgBorder"]
    > [![Partial screenshot of the list of views for the Account table, showing the New view option.](../media/new-view.png)](../media/new-view.png#lightbox)

1. Define a **Name** and a **Description** for the new view. Select **Create** to proceed to the view designer.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Create a view form. The Name and Description fields are filled in and the Create option is highlighted.](../media/create-name.png)](../media/create-name.png#lightbox)

1. Add columns to the view, including **Annual Revenue** and **Owner**.

    > [!div class="mx-imgBorder"]
    > [![Partial screenshot of the view designer. Focus is on the Actual Revenue column being selected from the flyout menu of add View column.](../media/add-columns.png)](../media/add-columns.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Partial screenshot of the view designer. Focus is on the Owner column being selected from the flyout menu of add View column.](../media/add-column.png)](../media/add-column.png#lightbox)

1. Set the order of the records to display in order of revenue. Select **Annual Revenue** and then select **Larger to smaller**.

    > [!div class="mx-imgBorder"]
    > ![Partial screenshot of the view designer. Focus is on the Actual Revenue column heading and the Larger to smaller option from the flyout menu.](../media/annual.png)

1. Filter the accounts to be displayed so that only the records that you manage are listed. Select the **Owner** column heading and then select **Filter by**.

    > [!div class="mx-imgBorder"]
    > ![Partial screenshot of the view designer. Focus is on the Owner column heading and the Filter by option from the flyout menu.](../media/owner.png)

1. In the list of users, select your name and then select **Apply**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of the Filter by flyout menu. Focus is on the selected user and the Apply option.](../media/apply-filter.png)

1. To apply changes and make them available to Power Apps users, select **Save > Publish**.

    > [!div class="mx-imgBorder"]
    > ![Partial screenshot of the view designer, showing the Save and Publish options being selected.](../media/save-publish.png)

## Exercise steps (video)

Watch the following video for a demonstration of the steps that you've completed for this exercise.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE59enu]

## Next steps

Now, you've learned how to add filter and sort criteria to a Dataverse table view. Next, you'll validate the learned concepts for this module.
