In this unit, you'll learn about the personas, scenarios, and different methods for Scope 3 Category 1 calculations that include the emissions from purchased goods and services. This category includes all upstream cradle-to-gate emissions from the production of products that have been purchased by the company in the reporting year, which for this scenario means the cradle-to-gate emissions of the coffee beans supplier and the participating farms.

Organizations can use any of the following four methods to account for Scope 3 emissions from purchased goods and services:

- **Supplier-specific method** - Collects product-level, cradle-to-gate GHG inventory data from goods or services suppliers.

- **Hybrid method** - Uses a combination of supplier-specific activity data (where available) and secondary data to fill the gaps where supplier data isn't available.

- **Average-data method** - Estimates emissions for goods and services by collecting data on the mass (such as kilograms or pounds) or other relevant units and then multiplying by the relevant secondary emission factors.

- **Spend-based method** - This method estimates emissions for goods and services. It does so by collecting data on the economic value of purchased goods and services and then multiplying it by relevant secondary (for example, industry average) emission factors.

For this exercise, you'll use the hybrid method for calculating the Scope 3 Category 1 emissions for Contoso, Texas. 
The important consideration for Contoso, Texas to choose Fourth Coffee is the sourcing relationship Fourth Coffee has with a consortium of environmentally friendly coffee farms.  

The consortium farms have paid for a study to be conducted to determine the average amount of CO<sub>2</sub>e that's generated for each metric ton of farmed coffee beans. On average, these farms generate 150 kg of CO<sub>2</sub>e for each metric ton of farmed coffee beans. However, to meet their demand, Fourth Coffee also sources from coffee farms that aren't a part of the consortium. 

With Fourth Coffee providing supplier-specific, averaged data for consortium farms, but not for non-consortium farms, Contoso needs to use a hybrid method of calculation. The hybrid method allows Contoso to provide more accurate emission calculations where possible for the consortium farms while still accounting for the emissions of the non-consortium farms by using a spend-based method.

## Personas and scenarios

The subsequent exercise features the following personas:

:::row:::
   :::column span="":::
      > [!div class="centered"]
      > :::image border="false" type="content" source="../media/devon.png" alt-text="Artwork showing a fictitious person named Devon Torres.":::
   :::column-end:::
   :::column span="":::
      > [!div class="centered"]
      > :::image border="false" type="content" source="../media/remy.png" alt-text="Artwork showing a fictitious person named Remy Morris.":::
   :::column-end:::
   :::column span="":::
      > [!div class="centered"]
      > :::image border="false" type="content" source="../media/riley.png" alt-text="Artwork showing a fictitious person named Riley Ramirez.":::
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      **Devon Torres** - Sustainability specialist for Contoso, Texas
   :::column-end:::
   :::column span="":::
      **Remy Morris** – Sustainability emissions analyst for Contoso, Texas
   :::column-end:::
   :::column span="":::
      **Riley Ramirez** - IT admin for Contoso, Texas
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      **Persona actions** - Performs data ingestion of a purchased goods data spreadsheet, works with Remy to create a new factor library for consortium farm emissions, creates a new hybrid calculation model that reflects the calculations for consortium and non-consortium farms, and then signs off on final calculation results.
   :::column-end:::
   :::column span="":::
      **Persona actions** - Prepares the purchased goods data spreadsheet from invoices that Fourth Coffee has provided, reviews the study that's conducted on Fourth Coffee consortium farms, and works with Devon to integrate the average emission findings into the category 1 calculations.
   :::column-end:::
   :::column span="":::
      **Persona actions** - Works with Devon to extend the **Purchased good and service** table to accommodate the new consortium farm data, and then creates the necessary calculation profile based on guidance from Devon.
   :::column-end:::
:::row-end:::
