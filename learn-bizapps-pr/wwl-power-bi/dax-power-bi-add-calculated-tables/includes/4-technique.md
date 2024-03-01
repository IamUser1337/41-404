There are three techniques that you can use to add columns to a model table:

- Add columns to a view or table (as a persisted column), and then source them in Power Query. This option only makes sense when your data source is a relational database and if you have the skills and permissions to do so. However, it's a good option because it supports ease of maintenance and allows reuse of the column logic in other models or reports.
- Add custom columns (using M) to Power Query queries.
- Add calculated columns (using DAX) to model tables.

Regardless of which technique you use, it results in the same outcome. Report users can't determine the origin of a column. Typically, they're not concerned with how the column was created but rather that it delivers the right data.

When multiple ways are available to add a column, you can consider using the approach that best fits your skills and that's supported by the language (M or DAX). However, the preference is to add custom columns in Power Query, whenever possible, because they load to the model in a more compact and optimal way.

When you need to add a column to a calculated table, make sure that you create a calculated column. Otherwise, we recommend that you only use a calculated column when the calculated column formula:

- Depends on summarized model data.
- Needs to use specialized modeling functions that are only available in DAX, such as the `RELATED` and `RELATEDTABLE` functions. Specialized functions can also include the [DAX parent and child hierarchies](/dax/understanding-functions-for-parent-child-hierarchies-in-dax/?azure-portal=true), which are designed to naturalize a recursive relationship into columns, for example, in an employee table where each row stores a reference to the row of the manager (who is also an employee).
