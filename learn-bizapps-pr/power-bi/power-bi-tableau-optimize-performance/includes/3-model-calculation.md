Calculated columns can be problematic, because you can technically create them in Query Editor or in Data Analysis Expressions (DAX) on Power BI Desktop. Usually, you have one deciding factor for determining when and where to create a calculated column: whether the calculated column involves more than one table. If the calculated column does involve more than one table, then use DAX; otherwise, Query Editor is optimized to handle a new column.

When you create the calculated column in the database, you get the benefits of compression, similar to any other column. If the calculated column is created with DAX, it'll act more like a measure and will be calculated and recalculated with every use. This process can decrease performance.

Often, improving calculations is more of an art than a science, but several methods are available to help you improve your calculation performance: variables, avoid iterator functions, and DAX Studio.

## Use variables

Variables are beneficial in helping to reduce interdependence and calculation time. If a calculation references a variable, it calculates the variable once instead of every time you use the calculation. Using variables also creates less interdependence between calculations.

> [!NOTE]
> Using variables will be a departure for many Tableau users because they nest their calculations.

## Avoid iterator functions

Iterator functions can be useful; however, because you're using columnar storage, any calculation that evaluates every row in your data will affect performance. To help optimize performance, make sure that you review your alternatives before using an iterator function.

## Improve performance with DAX Studio

If you're looking to improve performance or syntax, you can use DAX Studio. DAX Studio is an external tool that has full integration with Power BI and can help evaluate your calculations' performance.
