To meet the supply demand of Texas and the Gulf Coast region in the US, Contoso, Texas has purchased two coffee roasting machines. It has purchased for its new manufacturing facility from Fabrikam, Inc for a net cost of `$927,198.46`. Additionally, they've purchased office furniture from VanArsdel, Ltd. for a net cost of `$27,977.00`. 

The purchase of the roasting and office equipment falls under Scope 3 Category 2 emissions that target all upstream, cradle-to-gate emissions of purchased capital goods. One challenge that organizations face is the ambiguity around the purchase of capital goods versus purchased goods and services. Organizations need to rely on financial accounting procedures to make this differentiation. Organizations must account for the emissions from the use of capital goods in Scope 1 or Scope 2.

Organizations can use four methods to calculate Scope 3 emissions from capital goods:

- **Supplier-specific method** - Involves collecting product-level, cradle-to-gate GHG inventory data from suppliers.

- **Hybrid method** - Involves the use of a combination of supplier-specific activity data and secondary data to fill the gaps for unavailable activity data. The secondary data could be from sources such as industry-average-data, financial data, proxy data, and other generic data.

- **Average product method** - Involves the estimation of emissions for goods by collecting data on the mass or relevant units of goods and then multiplying by relevant, industry-based emission factors. 

- **Average spend-based method** - Involves the estimation of emissions for goods by collecting data on the economic value of purchased goods and then multiplying it by relevant, secondary emission factors. 

For this exercise, you'll use the **Average spend-based** method for calculating the Scope 3 Category 2 emissions for Contoso, Texas. The reason why you're using this method is because the supplier hasn't provided you with the product level emissions data. Also Contoso has a factor library that's included with Microsoft Sustainability Manager that contains Average spend-based emission factors, EPA 2022 - Supply chain GHG emission factors - v1.1. 

An important concept for using this method is the US Environmentally-Extended Input Output (USEEIO) models, or simply EEIO. A family of models, EEIO, designed by the US Environmental Protection Agency (EPA) blends economic transactions with a wealth of environmental information. For more information, see the [US Environmentally-Extended Input-Output (USEEIO) Models | US EPA](https://www.epa.gov/land-research/us-environmentally-extended-input-output-useeio-models/?azure-portal=true). Alternatively, you can also bring Contoso's own, or an external, EEIO or other factor library. For more information, see [Emission factors](/industry/sustainability/calculate-emission-factors?azure-portal=true#custom-emission-factors).

## Persona and scenarios

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
      **Persona actions** - Performs data ingestion of the capital goods data spreadsheet, reviews built-in calculation models, selects a fitting model, and signs off on final calculation results.
   :::column-end:::
   :::column span="":::
      **Persona actions** - Prepares the capital goods data spreadsheet from the purchased equipment invoices.
   :::column-end:::
   :::column span="":::
      **Persona actions** - Works with Devon to create the necessary calculation profile.
   :::column-end:::
:::row-end:::
