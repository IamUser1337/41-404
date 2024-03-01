The estimated time to complete this lab is 35 minutes.

## Connect to data

1. Open Power BI Desktop.
1. Select **Get data**.
1. Highlight **Excel** and select **Connect**.
1. Navigate to *D:\Power-BI-Tableau\Lab-02\Data*.
1. Open *raw_TailspinToys2019-US.xlsx*.
1. Select the following tables and select **Load**.

   - **dbo_Region**
   - **2017_Sales**
   - **2018_Sales**
   - **2019_Sales**
   - **Product Details**

   > [!NOTE]
   > What is the difference between **dbo_Region** and **Region**? **dbo_Region** is defined in Excel as a table. **Region** refers to the entire Excel tab named *Region*.

   The loaded tables appear in the **Fields** pane.

1. Select the table icon to open the Data view.

   :::image type="content" source="../media/lab-1-data-preview.png" alt-text="Screenshot of the table icon on the left.":::

   Look through each data table you loaded to familiarize yourself with the data. Is there anything you would change?

## Transform data

1. From the **Home** ribbon, select **Transform data**. The Power Query Editor opens.

   :::image type="content" source="../media/lab-2-transform-data.png" alt-text="Screenshot of the Power BI tool ribbon with Transform data highlighted." lightbox="../media/lab-2-transform-data.png":::

1. Under **Queries**, select **Product Details**.

   The changes made to the data are recorded under **Applied Steps**. You haven't made any changes, but there are already applied steps. By default, when Power BI Desktop loads an Excel file, M code is written to load the data correctly and read the headers.

### Clean and pivot product table: transpose and trim

The product data doesn't have column headers. It has row headers. This situation is hard to work with.

1. In the **Transform** ribbon, select **Transpose**.
1. Select **Use First Row as Headers**. Now you have a dimension table for product.
1. Under **Properties**, rename the table *Product*.
1. Look at the **ProductCategory** column. There are leading spaces. To tidy up this data, select the column and right-click. From the context menu, select **Transform** > **Trim**.

### Sales data: append

It's easier to plot time trends and perform year-over-year calculations when all your historical sales data is in one location.

1. Select **2019 Sales**. In the **Home** ribbon, select **Append Queries**.
1. In the **Append** dialog box, select **Three or more tables**.
1. Add **Sales 2018** and **Sales 2017** to **Tables to Append** Select OK.
1. Ensure that you have all three years of data.
   1. In the **OrderDate** column, select the down arrow to open the context menu for the column.
   1. Select **Load More**. You should see dates for 2017, 2018 and 2019 in the same data source.
   1. Select **OK** to close the menu.
1. Under **Properties**, rename the query *Sales*.
1. Under **Queries**, right-click **2017 Sales** and unselect **Enable Load**. If a warning dialog box opens, select **Continue**.
1. Do the same for **2018 Sales**.

   There's no need to load the 2017 and 2018 data into the report multiple times. All the information is available in the new **Sales** table.

### Create a customer dimension table: duplicate, remove duplicates, rename columns

There are customer details on the **Sales** table. These details are long text string data repeated for every customer. This situation is when a dimension table is useful. The table eliminates the need to store duplicate information.

1. Under **Queries**, select **Sales**.
1. Select and drag the **CustomerStateID** column to the left of the column **first_name**.
1. Under **Queries**, right-click **Sales**. From the context menu, select **Duplicate**. 
1. Right-click **Sales (2)** and select **Rename**.  Rename it *Customer*.
1. In the **Customer** table, hold **Ctrl** and select the following columns: **CustomerStateID**, **first_name**, **last_name**, and **email**.
1. Right-click the column headers and select **Remove Other Columns**.
1. Right-click the **email** column header. From the context menu, select **Remove Duplicates**.
1. Select the down arrow on **email** and select **Remove Empty**. This action removes blank and null values, which aren't good to have in dimension tables.

1. Right-click the email column header and select **Add Columns From Examples**.

1. Rename this new column **Company**.

1. Begin to type in the company name that you assume goes with the customer's email address. For example, with `fdodgson@contoso.com`, the assumed company is `Contoso`.

   :::image type="content" source="../media/lab-3-company-email.png" alt-text="Screenshot of Add Column from Examples with Email selected." lightbox="../media/lab-3-company-email.png":::

   Now you have a simple table of key customer information.

1. Remove the columns **CustomerStateID**, **first_name**, and **last_name** from the **Sales** query. Be sure to leave **email**. This column is your only unique indicator to join the **Customer** table to the **Sales** information.

### Combine state and region dimension: join

You have two references to **StateID**, but no State name: **Customer.CustomerStateID** and **Sales.OriginationStateID**.

1. From the **Home** ribbon, select **New Source**.
1. In the **Get Data** dialog box, select **Text/CSV**, then **Connect**.
1. Select *state_lookup.csv*, then **Open**.
1. Select **OK**.

The **dbo_Region** and the **state_lookup** query create simple dimension tables. For simplicity, combine them into a new table named **Geography**.

1. Under **Queries**, select **state_lookup**.
1. From the **Home** ribbon, select **Merge Queries**.

   :::image type="content" source="../media/lab-4-merge-queries.png" alt-text="Screenshot of the Power Query Editor ribbon with Merge Queries highlighted." lightbox="../media/lab-4-merge-queries.png":::

1. In the **Merge** dialog box, select **dbo_Region** to merge.
1. Select the **RegionID** column in both **state_lookup** and **dbo_Region** table. You should see that 51 out of 51 records in the state_lookup table are matched.

   :::image type="content" source="../media/lab-5-merge-pane.png" alt-text="Screenshot of the Merge dialog with state_lookup and dbo_Region selected and the Join Kind set to Left Outer." lightbox="../media/lab-5-merge-pane.png":::

   After the tables are joined, all the fields from **dbo_Region** are in a single column.
1. Select the diverting arrows in the column header. Then make sure only **RegionName** is selected.
1. Unselect **Use original column name as prefix** and select **OK**.

   :::image type="content" source="../media/lab-6-add-region.png" alt-text="Screenshot of the arrows to the right of Region with the dropdown showing RegionName selected and Use original column name as prefix cleared." lightbox="../media/lab-6-add-region.png":::

1. Rename the **state_lookup** table *Geography*.

1. Select the **RegionID** header, right-click, and select **Remove**.

1. Under **Queries**, right-click **Geography** and unselect **Enable Load**. Select **Continue** when the warning dialog box appears.

   Because the **Geography** dimension table includes the region information you need, you don't have to load the table.

### Set relationships

1. Select **Close and Apply**. This action closes the Query Editor and loads your changes into the Power BI Desktop and any reporting in that file.

1. Select the **Data** icon to open Data view.

   :::image type="content" source="../media/lab-7-data-model-icon.png" alt-text="Screenshot of the Data Model icon on the left.":::

1. Rearrange the tables so they look approximately like the following example:

   :::image type="content" source="../media/lab-8-data-model.png" alt-text="Screenshot of tables arranged with Geography at the top left, Customer at bottom left, Product at top right with a join to Sales in the center." lightbox="../media/lab-8-data-model.png":::

## Summary

As a result of this lab, you should have the following data sources available to use in our report.

- Product
- Geography
- Customer
- Sales

In the data modeling pane, you should see the following tables.

:::image type="content" source="../media/lab-8-data-model.png" alt-text="Screenshot of tables arranged with Geography at the top left, Customer at bottom left, Product at top right joined to Sales in the center." lightbox="../media/lab-8-data-model.png":::

## Data Definitions

In Excel:

- **ProductDetails.WholesalePrice** = What Tailspin Toys paid to make or acquire the product
- **Sales.UnitPrice** = The undiscounted cost of product for customers *per unit*
- **Sales.DiscountAmount** = A discount available that should be subtracted from **UnitPrice** *per unit*
- **SaleAmt** = The discounted price the customer pays **UnitPrice** - **DiscountAmount**
