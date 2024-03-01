Watch the following video to learn about iterator functions.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4AkNG]

Data Analysis Expressions (DAX) include a family of functions known as *iterator functions*. Iterator functions enumerate all rows of a given table and evaluate a given expression for each row. They provide you with flexibility and control over how your model calculations summarize data.

By now, you're familiar with single-column summarization functions, including `SUM`, `COUNT`, `MIN`, `MAX`, and others. Each of these functions has an equivalent iterator function that's identified by the "X" suffix, such as `SUMX`, `COUNTX`, `MINX`, `MAXX`, and others. Additionally, specialized iterator functions exist that perform filtering, ranking, semi-additive calculations over time, and more.

Characteristic of all iterator functions, you must pass in a table and an expression. The table can be a model table reference or an expression that returns a table object. The expression must evaluate to a scalar value.

Single-column summarization functions, like `SUM`, are shorthand functions. Internally, Microsoft Power BI converts the `SUM` function to `SUMX`. As a result, the following two measure definitions will produce the same result with the same performance.

```dax
Revenue = SUM(Sales[Sales Amount])
```

```dax
Revenue =
SUMX(
    Sales,
    Sales[Sales Amount]
)
```

It's important to understand how context works with iterator functions. Because iterator functions enumerate over table rows, the expression is evaluated for each row in row context, similar to calculated column formulas. The table is evaluated in filter context, so if you're using the previous **Revenue** measure definition example, if a report visual was filtered by fiscal year **FY2020**, then the **Sales** table would contain sales rows that were ordered *in that year*. Filter context is described in the filter context module.

> [!IMPORTANT]
> When you're using iterator functions, make sure that you avoid using large tables (of rows) with expressions that use expansive DAX functions. Some functions, like the [`SEARCH`](/dax/search-function-dax/?azure-portal=true) DAX function, which scans a text value that looks for specific characters or text, can result in slow performance. Also, the [`LOOKUPVALUE`](/dax/lookupvalue-function-dax/?azure-portal=true) DAX function might result in a slow, row-by-row retrieval of values. In this second case, use the [`RELATED`](/dax/related-function-dax/?azure-portal=true) DAX function instead, whenever possible.
