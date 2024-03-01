
| **Calculated Columns** | **Measures** |
|--|--|
| A new column is usually created as a function of other columns. | An aggregated value created with DAX functions. |
| Always associated with a table. | Not associated with a table. |
| Evaluated upon creation. | Evaluated when visual is built. |
| Computed at the row level of the table it's associated with. | Aggregate based on row and filter context: what is on your report page. |

**Differences between calculated columns and measures.**

With calculated columns, you can add new data to a table already in your Power BI model. You'll be exploring some common use-cases: conditional columns, arithmetic between columns, and columns that are dependent on multiple tables.

**Video**: Demo of calculated columns
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWy75w]

## Create conditional columns

Conditional columns allow analysts to test logical scenarios of variables; they help determine if a certain condition is true or false. The most simple way to think about conditional columns would be through the logical functions, like the IF function. This function checks a condition, and returns one value when it's TRUE, otherwise it will return a second value.

Here's an example of a conditional column:

`Active StoreName = IF( [Status] = "On", [StoreName], "Inactive" )`

In the previous snippet of code, you're checking to see whether the status field for a store is set to "on." If that statement is true, then you want to display its store name. Otherwise, you'll display the phrase "inactive."

> [!TIP]
> CORRELATING TO TABLEAU: This concept should be familiar in the Tableau calculated field window. In Tableau, you can do conditional statements using IF/THEN syntax and/or the IIF function. The IF function in Power BI is most like the IFF function in Tableau.

## Perform arithmetic between columns

Performing arithmetic in the calculated columns should be familiar to Tableau analysts, however the syntax will be different for some functions.

The following code is an example of a calculated column using familiar syntax:

`DiscountedPrice = [FullPrice] - [Discount]`

Based on the previous code, "DiscountedPrice" is a calculated column that returns the discounted price for an item. It does so by subtracting an item's applied discount from its full price.

On the flip side, the following code is an example of a calculated column with different syntax:

`ProfitRatio = DIVIDE( [Profit], [Sales] )`

> [!TIP]
> CORRELATING TO TABLEAU: In Tableau calculated fields, you perform division by using the "/" character: `ProfitRatio = [Profit] / [Sales]`

## Create calculated columns dependent on multiple tables

Power Query is a data connection technology that enables analysts to discover, connect, combine, and refine data sources. With that information, it would make sense to use Power Query to create columns that are dependent on multiple tables. Unfortunately, this isn't possible with Power Query.

To bridge this gap in Power BI, analysts need to use DAX because you're creating a calculation that uses the relationships that you set up in Power BI Desktop.

### Cost of Goods Sold example

For example, you have been given a new task where you need to calculate the Cost of Goods Sold (COGS), that uses the product wholesale price and the number of units sold. The product wholesale price will be found in the product dimension table and the number of units sold will be from a sales fact table. Here's a data preview of all the pieces together in this example:

> [!div class="mx-imgBorder"]
> [![Data preview of the COGS example.](../media/cogs.png)](../media/cogs.png#lightbox)

The following snippet of code is an example of a calculated column dependent on multiple tables:

`COGS = Sales[Quantity] * RELATED( Product[Wholesale Price] )`

> [!TIP]
> CORRELATING TO TABLEAU: The ensuing snippet of Tableau code will only work if the data is blended on the [ProductID] dimension from the [Product] table: `COGS = [Quantity] * [Product].[Wholesales Price]`

> [!TIP]
> CORRELATING TO TABLEAU: If the data is de-normalized in Tableau Desktop, your code would look something like the following: `COGS = { FIXED [ProductID]: SUM([Quantity] * [Wholesale Price]) }`

The RELATED function allows users to use values from other tables in calculated columns or measures, based on an existing relationship.

We review these steps in the following video:

**Video**: Creating a calculate column
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWy75x]

Another relationship function you might use is USERELATIONSHIP, which overrides other relationships only for the duration of the calculation. In other words, it enables the indicated relationship (based on the parameters or two column names) for the duration of the calculation.

## Understand measures

Measures are going to be a little different when compared to calculated columns. Measures are not calculated by every row - they're calculated based on an aggregation.

**Video**: Demo of creating a measure
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWy75B]

| **Measures** | **Definition** |
|--|--|
| = SUM( Sales[Quantity] ) | Sums the Quantity column in the Sales table.|
| = SUMX( Sales, (Related( Product[Wholesales Price] ) * Sales[Quantity] ) ) | Look up Wholesale Price in the Product table and multiply it by the Quantity in the Sales table (iterates through each row, then sums). This assumes referenced tables have relationships.|
| = [Total Sales] -- [COGS] | Subtracts COGS measure from Total Sales Measure (both must be measures and not calculated columns). |
| = DIVIDE( [Gross Profit], [Total Sales] ) | Divides the Gross Profit measure by the Total Sales measure. |
| = SWITCH( DATE[Month], 1, "January", 2, "February", 3, "Unknown month number" ) | Short-hand way to create IF/THEN statements with many conditions. |

**Examples of simple measures using common functions, along with their definitions.**

### Reference links

For more information on calculated columns, see: [Create calculated columns in Power BI Desktop](/power-bi/transform-model/desktop-calculated-columns/?azure-portal=true)

For more information on DAX, see: [Use DAX in Power BI Desktop](/training/paths/dax-power-bi/?azure-portal=true)
