
In this unit, you create a model-driven app by using one of the standard entities that are available in your Microsoft Power Apps environment.

> [!IMPORTANT]
> This hands-on lab assumes that you have a Dataverse instance that you can work with. If you don't have an instance you can work with, you can obtain a 30-day Power Apps trial plan [here](/power-apps/maker/signup-for-powerapps).

> [!IMPORTANT]
> If you sign up for a Power Apps trial using your company email address, and your company is already using Power Apps, your trial will be added to your organization's current tenant.  If your current Microsoft account doesn't already have the necessary permissions, you may not be able to add tables to your trial. In these instances, you can sign up for a new trial account that doesn't use your work or school account. You can find instructions on how to do this [here](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RW16PhH).

## Create a model-driven app

### Create a blank model-driven app

1. Sign in to [Power Apps](https://make.powerapps.com/) by using your organizational account.

2. Select the environment you want or go create a new one.

3. Using the navigation on the left, select **+ Create**.

4. On the **Create your app** page, in the **Start from** section, select **Blank App**.

5. On the Create screen, select **Blank app based on Dataverse**, and click **Create**.

	:::image type="content" source="../media/03-describe-building-power-apps-29.png" alt-text="Screenshot of model-driven app from blank.":::

6. On the **New model-driven app** page, enter a **name** and **description** for the app. (For example, enter "My first app" for the name, and "My first model-driven application" for the description.)

7. After a few minutes, your new app will appear.

	:::image type="content" source="../media/03-describe-building-power-apps-30.png" alt-text="Screenshot of model-driven app designer.":::

### Add Account table to your app

You can add pages to your app by using the App Designer.

8. If necessary, using the navigation on the left, select the **show or hide menu names button** (looks like 3 horizontal lines) to show the menu names.

9. Select the **Group1** text. On the right-hand side of the screen change the Title to **Customers**.

	:::image type="content" source="../media/03-describe-building-power-apps-31.png" alt-text="Screenshot of renaming the customer group.":::

10. Using the command bar at the top, select the **+ Add Page** button.

11. On the Add Page screen, select **Table based view and form,** then select the **Next** button.

12. On the Add table view and form pages screen, select **Account** then select the **Add** button.

> [!NOTE]
> Your environment may not contain an account table. If that's the case, you'll need to create one. Use the navigation on the left and select **Dataverse**, expand, and select **Tables** On the top action bar, select **New table**. In the form that appears, add in Account in the Display name field and **Save**.  

:::image type="content" source="../media/03-describe-building-power-apps-32.png" alt-text="Screenshot of how to create an Account table.":::

### Add forms and views to your app

Now that we added a table to our app, we're going to specify which Account forms and views should be used with the application.

13. Using the navigation on the left, select **Pages.**

14. Expand **Account** and select **Account** form.

15. On the right-hand side of the screen, select **Add form**.

16. From the list of Forms that appears, select **Account.**

	:::image type="content" source="../media/03-describe-building-power-apps-33.png" alt-text="Screenshot of Account main form.":::

17. Under **Pages** on the left, select **Account** view.

18. On the right-hand side of the screen, select **Add view**.

19. Select the **My Active Accounts** view.

20. Select **Add view** again.

21. Select **Active Accounts**.

22. Select **Add view**.

23. Select **Inactive Accounts.**

	- My Active Accounts

	- Active Accounts

	- Inactive Accounts

### Add Contact page to your app

Next, we're going to add another table to our application. In this case, we're going to add the Contacts table since a customer could be either an account or a contact.

24. On the command bar at the top, select the **Add Page** button.

25. On the Add page screen, choose **table-based view and form**, then select the **Next** button.

26. In the **Search** field, enter **Contact**, then select the **Contact** table.

27. Select the **Add** button.

### Save and publish your app

Now that you successfully created your first model driven application, let’s get ready to use it.

28. Using the command bar at the top select the **Save** button.

29. Once your application is saved, select the **Publish** button.

30. To test your application, select the **Play** button.

> [!NOTE]
> It's possible that you won't have any data in your environment. Select either Account or Contact and add a few sample records to test functionality.
