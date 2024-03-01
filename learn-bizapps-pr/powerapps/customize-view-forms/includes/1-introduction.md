 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RWSJjU]

Previously, by using a Microsoft Excel worksheet as the method to track company accidents, people could view and review logged accidents. This method also offered users the ability to filter the Excel rows based on the cell's criteria. Currently, the role of a table view is to give the user that same ability in the model-driven app. With views, users can review accident records without the risk of overriding or deleting data or causing errors, which are common issues in Excel.

>[!NOTE]
> If you haven't completed the previous modules within this learning path, download the [packaging files](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/tree/master/power-apps/customize-views-forms). These files contain the completed work on the Accident Tracking app thus far.

Views define how a list of records for a specific table will appear in your app. Additionally, views define the columns that are shown and the width, sort behavior, and default filters of the records that are shown in the list. Views are a way for you to present data to the user for review only.

> [!div class="mx-imgBorder"]
> [![Screenshot showing a sample view of the accident tracking table.](../media/1-accident-table.png)](../media/1-accident-table.png#lightbox)

The tables that you created in the previous module have a set of default views that you can use to show meaningful data to the users. In this module, you'll focus on modifying these default views; however, keep in mind that the same concepts would apply if you wanted to create a new custom view(s). For more information, see [Understand model-driven app views](/power-apps/maker/model-driven-apps/create-edit-views/?azure-portal=true).

Now that you have an overview of views, you can begin your first exercise and observe how to modify a default table view.

### Modify default table views

In this section and the next exercises, you'll modify the standard views from the tables that you created in the Build the Dataverse table schema for the model-driven app module. You'll turn these views into the one place where app users can review the data that is stored in the tables. Then, you'll make sure that the presented data is organized and relevant to the app user. For example, you want to make sure that the app user can review all data that is relevant for an employee under one concise list.

Sign in to Microsoft Power Apps and then follow these steps to modify default views:

1. To get started, go to [https://make.powerapps.com](https://make.powerapps.com/?azure-portal=true) and sign in with your Microsoft credentials.

1. In the left navigation pane, expand the **Dataverse** menu and then select **Tables**.

1. Scroll until you find the **EmployeeTable** that you created in the previous module. You can also search for it by typing **employee** in the search field at the top right of the screen.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the filter and the search bar in Microsoft Dataverse.](../media/2-custom.png)](../media/2-custom.png#lightbox)

1. After you have located **EmployeeTable**, select it, and then select **Views**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of views in data experiences.](../media/select-views.png)](../media/select-views.png#lightbox)

1. Locate and select the **Active EmployeeTables** view. You'll be redirected to the Microsoft Dataverse view designer studio.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Employee Table view with Active Employee Tables highlighted.](../media/3-active-tables.png)](../media/3-active-tables.png#lightbox)

    > [!NOTE]
    > Under the **View** type are several different types of views. Essentially, the different view types present the same information, but it might be filtered on **active** versus **inactive** employees or some other filters. You can mix these views so that users can select from them as preset filters to find relevant data more easily in the model-driven app. For this exercise, you will modify one view.

   In design mode, the left side of the screen under the **Table columns** header will show a list of columns from the **EmployeeTable** and a main grid on the form canvas itself (like an Excel sheet) that shows the selected columns.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the left navigation pane showing columns from the Employee Table.](../media/4-design-mode.png)](../media/4-design-mode.png#lightbox)

    The goal will be to select the columns that will be relevant to users when they want to review employee information. You'll customize the view to include employee name, employee date of birth, employee ID, and employee email.

1. By default, this view already has the **EmployeeId** column and the **Created On** column. Select the **Created On** column, and from the dropdown menu, select **Remove**. The **Created On** column will no longer show in the view. Notice how the column shows up under the **Table columns** header when it's removed. So, if you accidentally remove one, it's easy to add it back.

1. Add the **EmployeeName** column to the view by selecting it. The column should now show as added to the grid.

1. Repeat the previous step for **EmployeeDOB** and **EmployeeEmail**. When you're finished, the screen should appear similar to the following screenshot with the fields showing on the grid.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of table fields highlighted in the top navigation bar.](../media/5-employee-fields.png)](../media/5-employee-fields.png#lightbox)

    You can also use your mouse to reorder the fields by dragging and dropping them.

1. In the upper-right corner, select **Publish** to save and publish your changes.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Publish option highlighted.](../media/6-publish.png)](../media/6-publish.png#lightbox)
