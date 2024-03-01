Relationships matter, especially when it comes to your data.

Relationships allow users to query data from multiple tables. The only way for this approach to work is through a matching field between the multiple tables. Power BI refers to this field as a *relationship field*.

:::image type="content" source="../media/relationships.png" alt-text="Screenshot shows a relationship view in Power BI with multiple relationship fields." lightbox="../media/relationships.png":::

**Video**: Demo of Advanced Editor
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWy75u]

Before you further explore the importance of the relationship field, you need to learn more about dimensional modeling, which helps you better structure your relationship model. By now, you should have hands-on experience creating a snowflake branch on your model. You should also have an understanding of the difference between dimension and fact tables and between normalized and denormalized tables.

If you haven't yet had the opportunity to learn these dimensional modeling concepts, the following sections provide a refresher.

## Snowflake schema

A *snowflake model*, or *snowflake schema*, is when many relationships occur between tables and you must pass through multiple relationships to get from one table to another. This model usually resembles a snowflake shape with fact tables, usually in the middle. One table is connected to multiple dimension tables.

The principle behind a snowflake model is the normalization of the dimension tables, removing low cardinality attributes and creating their own tables. The following screenshot shows an example of a snowflake model.

:::image type="content" source="../media/snowflake.png" alt-text="Screenshot shows an example of a Snowflake schema in Power BI Desktop." lightbox="../media/snowflake.png":::

### Fact tables

The previous schema has only one fact table: **Sales Fact**. This **Sales Fact** table contains measures, or the quantitative attributes, such as the **Discount**, **Quantity**, and **Total** fields. The **Sales Fact** table also contains the relationship fields, or *foreign keys*, that allow users to refer to other dimension tables in the schema. For example, if you need to find out the total sales for a customer, you need to use the **CustomerID** fields in the **Sales Fact** table and the **Customer Dim** table.

### Dimension tables

The snowflake schema includes seven dimension tables:

- Time Dim
- Product Dim
- ProductCategory Dim
- Customer Dim
- City Dim
- Employee Dim
- Department Dim

Each dimension table contains unique, descriptive attributes that provide more meaning to the measures in the **Sales Fact** table, such as **CustomerID**, **EmployeeID**, and **ProductID**. With these fields, you could find out which product is purchased the most by distinct customers.

### Normalized tables

A *normalized table* is a table that was created in line with a series of normal forms. This approach reduces data redundancy and improves data integrity. In the same snowflake model, the data redundancy isn't present in the dimension tables. Each dimension table has its own unique attributes.

Power BI-specific relationships are the link, or communication channel, between your created tables. You have control over them. You can control the direction of the relationship and the fields.

## Relationship types

The three relationship types are *one-to-one* (1:1), *one-to-many* (1:\*), and *many-to-many* (\*:\*).

- A one-to-one relationship means that each record in a table relates to one, and only one, record in another table. For example, in the snowflake model, each customer has only one customer ID.

- A one-to-many relationship means that a record in one table can relate to zero, one, or many records in another table. For example, in the snowflake model, one customer could have multiple addresses. Perhaps the customer has moved multiple times or the customer has made purchases that use the different addresses.

- A many-to-many relationship means that zero, one, or many records in one table can relate to zero, one, or many records in another table. In reference to the previous snowflake model, customers can purchase various products, and many customers can purchase products.

## Tableau compared to Power BI

Typically, Tableau uses one, large normalized table. You can set up joins ahead of time, but your joins magnify your table, making it bigger and longer. The result is a *denormalized* table. Until 2018, if you wanted to do pseudo-dimensional modeling, the only way that you could accomplish that task was through data blending.

If you had an ID field in a dimension table, and you had an extensive denormalized table, you could link them through what Tableau calls a "relationship." This relationship would create a link icon in the dimensions pane in Tableau Desktop, which indicates which fields are being used in the data blend. Though this feature is convenient, ultimately, it isn't common practice in the Tableau Community.
