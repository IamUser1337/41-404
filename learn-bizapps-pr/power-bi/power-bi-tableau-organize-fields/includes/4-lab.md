The estimated time to complete this lab is 15 minutes.

In this lab, you'll create a hierarchy and bins from a field. You'll also create a measures table to store future calculations and update fields and tables to make them easier to use.

## Exercise 1: Organize your data

In this exercise, you'll organize and clean up your data for better usage.

### Task 1: Create a hierarchy

In this task, you'll create a product hierarchy.

1. From **Data** section, right-click or select the ellipsis next to **ItemGroup** field from **Product** table. Select **Create Hierarchy**.

    :::image type="content" source="../media/lab-01-new-hierarchy.png" alt-text="Screenshot of the ItemGroup menu with the New hierarchy option.":::

1. From **Data** section, right-click on your new Hierarchy and select **Rename**. Rename this field to "Product Hierarchy"

1. From **Data** section, drag and drop **ProductCategory** field from **dbo_Product** onto the "Product Hierarchy" or right-click and select **Add to Hierarchy**.

1. From **Data** section, drag and drop **KitType** field from **Product** onto the "Product Hierarchy" or right-click and select **Add to Hierarchy**.

1. From **Data** section, drag and drop **ProductName** field from **Product** onto "Product Hierarchy" or right-click and select **Add to Hierarchy**.

### Task 2: Create Bins

1. From **Data** section, right-click or select the ellipsis next to **Wholesale Price** field from **Product** table. Select **New group**

1. From the **Group** window, set the **Bin size** to 50.

    :::image type="content" source="../media/lab-07-bin-size-setting.png" alt-text="Screenshot of the Bin size option set to 50.":::

1. From the **Group** window, select OK to close.

### Task 3: Create a measures table

1. From the **RIBBON** under **Modeling > Calculations**, select **New table**.

1. From the **CALCULATION** section, name the table "Measures Table" and select the checkmark.

    :::image type="content" source="../media/lab-10-name-the-table.png" alt-text="Screenshot of the table with the name set to measures table.":::

1. You should now see a new table in the **Data** section.

1. From **Data** section, select one of the measures you created in the Calculations Module.

1. From the **RIBBON** under **Measure Tools > Structure > Home Table**, select your new **Measures Table**. This moves your measure.

1. Repeat these last two steps to move your other measures to your new **Measures Table**.

    > [!NOTE]
    > If this process throws an error for any of your calculations, edit them to make sure they reference the new measures tables instead of their original table.

1. From the **Data** section, right-click the empty **Column** field from **Measures Table** and select **Hide**.

### Task 4: Clean up fields

1. From the left pane, select the **Model**.

1. From the Geography table, select **StateName**. In the **Properties** pane under **General > Name**, rename the field to "State". In the **Properties** pane under **Advanced > Data Category**, set it to **State or Province**.

1. From the **Geography** table, right-click on **StateID** and select **Hide in Report View**.

1. From the Geography table, select **RegionName**. In the **Properties** pane under **General > Name**, rename the field to "Region".

1. From the **Product** table, select **ProductName**. In the **Properties** pane under **General > Name**, rename the field to "Product". In the **Properties** pane under **Advanced > Sort by column**, change it to "ProductID".

1. From the **Measures Table** table, select **Discount %**. In the **Properties** pane under **Formatting > Percentage format**, set to Yes.

1. From the **Sales** table, select **DiscountAmount**. In the **Properties** pane under **General > Name**, rename the field to "Discount Amount". In the **Properties** pane under **Formatting > Format**, change it to "currency" and set **Decimal places** to 0.

1. From the **Sales** table, select **OrderDate**. In the **Properties** pane under **General > Name**, rename the field to "Order Date". In the **Properties** pane under **General > Description**, write "Date the order was placed by the customer". In the **Properties** pane under **Formatting > Date Time Format**, select the numeric shorthand (m/d/yy).

    :::image type="content" source="../media/lab-10-name-the-table.png" alt-text="Screenshot of the All date formats dropdown with the month day year option selected.":::

1. From the **Sales** table, right-click on **OriginationStateID** and select **Hide in Report View**.

1. From the **Sales** table, right-click on **ProductID** and select **Hide in Report View**.

## Summary

In this lab, you created a new product hierarchy and created bins from a numeric field. You also created a measures table to store your calculations and cleaned up the tables.
