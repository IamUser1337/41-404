In this exercise, you'll set up the Retail churn model in the Dynamics 365 Customer Insights - Data environment that you created in the previous exercise.

## Task 1: Add a data source

In this task, you'll add a data source for your Retail churn model.

1. Open a new tab in your internet browser and navigate to the Microsoft Cloud [Solution Center](https://solutions.microsoft.com/)  

1. Expand **Retail,** and select **Unified customer profile**. 

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Customer Insights environment, showing the Add data source button.](../media/add-data-source.png)

1.  Check **Add** next to Retail channel churn model and then select **Deploy**.

1. Select the **Customer Insights Environment** that you created in the previous exercise, provide a name for your deployment, agree to the terms and conditions, and select **Next**.
 
1. Select **Microsoft Power Query**. Save the data source as **RetailGroceryChurn**, and then select **Next**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of Microsoft Power Query selected and the data source set.](../media/power-query-data-source.png)

1.  Select the **Azure Blobs** connector.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of Azure Blobs set as the connector.](../media/azure-blobs.png)

	Use the following steps to retrieve the **Storage Account name** and **Access Key** from the storage account that you created in [Exercise - Create a storage account and upload the input data files, Task 1: Create storage account](/training/modules/retail-churn-model/create-storage-upload-data/?azure-portal=true), and then update them in the **Azure Blobs** connection settings in Customer Insights.

1.  Open a new internet browser tab and then go to the [Azure portal](https://ms.portal.azure.com/?azure-portal=true).

1.  Under Azure services, go to **Storage accounts**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Azure services list, showing the Storage accounts option.](../media/azure-services.png)

1.  Search for **retailchurn** and then open the storage account.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the storage accounts with search results.](../media/storage-accounts.png)

1.  Select the **Access keys** area and then copy the **Storage account name**. Paste that name in the **Account name** field under the **Connection settings** in Customer Insights.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Access keys area with Storage account name displayed.](../media/access-keys-storage-account-name.png)
	
	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Connection settings dialog with the Account name field populated.](../media/connection-account-name.png)

1.  Return to the Azure portal, select **Show keys**, and then copy **key 1**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Show keys option, with key 1 copied.](../media/key.png)

1.  Paste the access key in the **Account key** field and the storage name in the **Account name or URL** field in the **Connection settings** dialog.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the account key added in the Connection settings dialog.](../media/account-key.png)

1.  Select **retailgrocery** and then select the **Transform data** button.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the data selected and the Transform data button.](../media/transform-data.png)

1.  Select the **\[Binary\]** link in the first cell of the first row for the **Grocery\_contact.csv** file.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the binary link in the first cell.](../media/binary.png)

1.  Go to the **Transform** ribbon and then select the **Use first row as headers** option.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Use first row as headers option in the Transform ribbon.](../media/first-row.png)

1.  Right-click the **birthdate** column, go to **Change type**, and then select **Date**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the birthdate column with the Change type menu and Date selected.](../media/date.png)

1.  Select the following columns by holding down the **Ctrl** key on your keyboard: **annualincome**, **msrc\_creditscore**, **msrc\_customerrelationshipduration**, and **msrc\_distancetoneareststore**. When these columns are highlighted, right-click one of them, go to **Change type**, and then select **Decimal number**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Change type set to Decimal number.](../media/decimal-number.png)

1. Under Properties on the right side, change the **Name** to **contact** and then press the **Enter** key on your keyboard. Don't save.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of Name being changed to contact.](../media/contact.png)

1. Right-click the contact query and then select **Duplicate**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the contact query menu with duplicate selected.](../media/duplicate.png)

1. Right-click the duplicated query and rename it to **transactions**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the duplicated query renamed to transactions.](../media/transactions.png)

1. With the **transactions** query selected, delete all **Applied steps** on the right up to the Navigation step.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the applied steps deleted.](../media/delete-steps.png)

1. Select the **\[Binary\]** link in the first cell of the third row for the **Grocery\_msrc\_transaction.crv** file.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the third row binary link.](../media/third-binary.png)

1. As before, go to **Transform** and select **Use first row as headers**.

1. Scroll to and select the **msrc\_transactiontimestamp** column. Right-click the column, select **Change type**, and then select **Date/Time**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the type changed to Date/Time.](../media/date-time.png)

1. Press and hold the **Ctrl** key on your keyboard to select the **msrc\_transactionamount** and **msrc\_discountappliedamount** columns. Right-click one of the columns, go to **Change type**, and then select **Decimal number**.

1. Right-click the **transactions query** and then select **Duplicate**.

1. Rename the query to **session** and then delete all **Applied steps** up to Navigation, as you did previously.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the query renamed to session and the applied steps deleted.](../media/session.png)

1. Select the **\[Binary\]** link in the first cell of the second row for the **Grocery\_msrc\_session.csv** file.

1. Go to **Transform** and select **Use first row as headers**.

1. Right-click **msrc\_sessiontimestamp**, go to **Change type**, and then select **Date/Time**.

1. Right-click the **msrc\_sessionduration** column, go to **Change type**, and then select **Decimal number**.

1. Right-click the **msrc\_sessioncustomersatisfaction** column, go to **Change type**, and then select **Whole number**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the type changed to whole number.](../media/whole-number.png)

1. Select **Save** and then monitor the data source as it refreshes. This step should take a few minutes.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Save button with the data source refresh.](../media/save.png)

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the validating queries message.](../media/validating-queries.png)

## Task 2: Unify your data
To unify your data, follow these steps:
1.  In Customer Insights, expand **Data** and then go to **Unify**. Under **Map**, select the **+ Select entities** button.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of Unify selected with the Map view and the Select entities button.](../media/select-entities.png)

1.  Select all three entities and then select **Apply**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the three entities selected and the Apply button.](../media/apply-entities.png)

1.  Select the **contact** entity and then select **contactid** as the primary key.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the primary key set as contact I D.](../media/primary-key.png)

1.  Select the **session** entity and then select **msrc\_sessionid** as the primary key.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the session entity primary key set.](../media/session-primary-key.png)

1.  Select the **transactions** entity and then select **msrc\_transactionid** as the primary key. Select **Save**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the transactions entity primary key set.](../media/transactions-primary-key.png)

1.  While in the **Unify** area, select **Match** and then select **+ Set order**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Match view with the Set order button.](../media/set-order.png)

1.  In the pop-up window, select **+ Add** in the lower part of the screen to add a third entity.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Add button to add a third entity.](../media/add.png)

1.  Select the entities in the following order: **contact**, **transactions**, and **session**. Ensure that the **Include all** checkbox is selected for all entities and then select **Done**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the entities selected, with the Include all checkbox selected for all three entities.](../media/include-all.png)

1.  Select **+ Add rule** next to the **transactions** entity.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Add rule button next to the transactions entity.](../media/add-rule.png)

1. Select **contactid** and **msrc\_customerid**, and then name the rule **contacttransactions**. Select **Done**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the rule details.](../media/rule-details.png)

1. Scroll down and select **+ Add rule** next to the session entity.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Add rule button next to the session entity.](../media/session-add-rule.png)

1. Select the **transactions** entity and then select the **msrc\_transactionid** and **msrc\_sessionid** fields. Name the rule **transactionssession** and then select **Done**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Create rule view for the transactions entity.](../media/transactions-entity-rule.png)

1. Select **Save**.

1. Select **Run**. This step will take several minutes to complete. When it's done, you’ll merge the data.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the completed process with success results.](../media/success-message.png)

1. Under **Unify**, select **Merge** and then select **Save**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of Merge view with the Save button.](../media/merge.png)

1. When the merged data is saved, select **Run** and then select **Run only Merge**. This process will take several minutes to complete.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Run menu with Run only Merge selected.](../media/run-only-merge.png)

Congratulations, the model should be visible and ready to train. Follow the next steps to train the model.

## Task 3: Train the model
To train the model, follow these steps:

1.  Go to **Predictions** on the left menu and then select **Create > Retail channel churn (preview) > Use model** button.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Use model button for Retail channel churn.](../media/use-model.png)

1.  In the pop-out pane, select the **Get started** button.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Get started button.](../media/get-started.png)

1.  Name the model and output entity to **RetailChurnModel**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the model name and output entity details.](../media/model-name.png)

1.  Adjust the model preferences as needed and then select **Next**.

1.  Select the **+ Add data** button below the **Customer** session on the middle pane. A right pane will open, where you can add the required customer data from the customer entity. Select **Save** when you’re done to return to the middle pane.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Add data button under the Customer session.](../media/add-data.png)

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the customer data details displayed in the Add customer data dialog.](../media/customer-data-details.png)

1.  Repeat the process with the data in the **Transaction** section. Select the second **+ Add data** button below the **Transaction** section on the middle pane. Fill out the transaction entity information on the right pane and then select **Save**. Select **Next** on the middle pane.

1.  When both required data entities are complete, select **Next** to go to the **Additional data** step.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of both data entities completed.](../media/complete-data-entities.png)

1.  Select **+ Add data** to enter information in the **Session** section. **Save** the data and then select **Next**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Add customer data window, with information filled in for the Session section.](../media/add-customer-data.png)

1.  Set the data update schedule as **Weekly** and then select **Next**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Data update schedule set to Weekly.](../media/weekly.png)

1. Confirm that everything looks correct and then select **Save and Run**.

1. Confirm that the model is running and then select **Done**.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Your model is configured and running message.](../media/configured-model.png)

1. Monitor the status of the request to determine when it's finished. You might receive an error on the first run. If you receive an error, run the prediction model again. It typically works on the second try.

1. You might receive an error on the first run, select **Refresh all** to run the model again.

	> [!div class="mx-imgBorder"]
	> ![Screenshot of a failed run message.](../media/error.png)

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Update predictions message.](../media/update.png)

	> [!div class="mx-imgBorder"]
	> ![Screenshot of the Refreshing status.](../media/refreshing-status.png)

 Congratulations, you’ve run the Retail channel churn predictive model.
