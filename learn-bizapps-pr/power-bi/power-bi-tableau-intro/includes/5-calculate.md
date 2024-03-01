The CALCULATE function is one of the most versatile functions in Power BI. The following example shows the CALCULATE function syntax:

```CALCULATE( <expression>, <filter1>, <filter2>, ... )```

The expression in the first parameter must be evaluated to return the result (a value) and is usually an aggregation function like SUM, AVG, MIN, etc. This expression is then evaluated in a context based on the filters. These filters can expand and limit the current evaluation context.

With the CALCULATE function, you have control over row and filter context. You can add, remove, and update filters. CALCULATE is the key function for many calculations in DAX.

## Add a filter with CALCULATE

The following code snippet shows an example of how to evaluate total sales and add an airplane filter context.

```Airplane Sales = CALCULATE( [Total Sales], 'Product Details'[ItemGroup] = "Airplane" )```

> [!TIP]
> The following code snippet shows how you would make the same calculation in Tableau:
>
> ```Airplane Sales = IF [ItemGroup] = "Airplane" THEN SUM([Sales Amount] ELSE 0 END```

## Update a filter with CALCULATE

The following code snippet shows an example of how to get "2018 Sales," even when 2019 is selected in a year slicer.

```2018 Sales = CALCULATE( [Total Sales], DATE[Year] = 2018 )```

> [!TIP]
> A direct Tableau comparison does not appear to be available. To complete this function in Tableau, you'd need to duplicate fields, bring in supplementary data sources, or perform calculations on each column.

## Ignore a filter with CALCULATE

The following code snippet shows an example of how to find the total sales in states that have Alexandria listed as a city ("Alexandria" is a value that's selected in a city slicer).

```Total Sales All States = CALCULATE( [Total Sales], ALL( Geography[State] ) )```

> [!TIP]
> You'd make the same calculation in Tableau by using the EXCLUDE LOD expression. Notice that this LOD expression is different from the other one by its granularity. With this expression, you'll want to exclude the state from the view instead of the state and city:
>
> ```Total Sales All States = { EXCLUDE [State] : SUM([Total Sales]) }```
