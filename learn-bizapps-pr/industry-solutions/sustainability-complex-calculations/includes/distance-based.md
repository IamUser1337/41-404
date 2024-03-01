In the previous exercise, you performed the Scope 3 Category 2 calculations for the purchase of coffee roasting equipment from Fabrikam Inc. In this exercise, you'll perform the calculations for Scope 3 Category 4 calculations that include the transportation and distribution of coffee beans that have been purchased from Fourth Coffee in Rio de Janeiro, Brazil. The coffee beans are shipped through sea route from Brazil to the Port of Houston through Tailwind Traders, and then they're transported by truck to the Contoso, Texas facilities in Houston and Fulshear through Northwind Traders. 

> [!IMPORTANT]
> The emissions from transportation and distribution from vehicles that are owned or controlled by the reporting company fall under Scope 1 (for fuel use) or Scope 2 (for electricity use). Scope 3 Category 4 is solely used for the upstream emissions from transportation and distribution through partner or other suppliers.

Organizations can use the following methods to calculate Scope 3 emissions from capital goods:

- **Fuel-based method** - Determines the amount of fuel that's consumed and then applies the appropriate emission factor for that fuel.

- **Distance-based method** - Determines the mass, distance, and mode of each shipment and then applies the appropriate mass-distance emission factor for the vehicle that's used.

- **Spend-based method** - Determines the amount of money that's spent on each mode of business travel transport and then applies secondary EEIO emission factors.

For this exercise, you'll use the **Distance-based** method for calculating the Scope 3 Category 4 emissions for Contoso, Texas. You're choosing a distance-based method because your suppliers have provided the mass, distance, and transportation mode details. You can use this extra information in the Scope 3 Category 4 emissions, enabling more accurate emission calculations than the **Spend-based** method. An important aspect of this calculation is the notion of **Stop count**, which is the number of stops that the transportation provider has made while shipping the goods.

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
      **Persona actions** - Performs data ingestion of the upstream transportation data spreadsheet, reviews built-in calculation models, copies and extends a default model, and then signs off on final calculation results.
   :::column-end:::
   :::column span="":::
      **Persona actions** - Prepares the upstream transportation data spreadsheet from invoices that the two transportation providers have provided. The spreadsheet includes mass measured by metric tons, distance traveled in miles, and number of stops made.
   :::column-end:::
   :::column span="":::
      **Persona actions** - Works with Devon to extend the Transportation and distribution table to accommodate the new stop count data and then creates the necessary calculation profile based on guidance from Devon.
   :::column-end:::
:::row-end:::
