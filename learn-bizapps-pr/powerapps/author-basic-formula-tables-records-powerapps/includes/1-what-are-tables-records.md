In Microsoft Power Apps, you can create a canvas app that accesses information in
Excel, SharePoint, SQL Server, and several other sources that
store data in records and tables. To work most effectively with this
kind of data, you need to learn more about the concepts that underlie these structures.

-   A *record* contains one or more categories of information about a
    person, place, or thing. For example, a record might contain the
    name, email address, and phone number of a single customer.
    Other tools refer to a record as a \"row\" or an \"item.\"

-   A *table* holds one or more records that contain the same categories
    of information. For example, a table might contain the names,
    email addresses, and phone numbers of 50 customers.

In your app, you'll use formulas to create, update, and manipulate
records and tables. You'll probably read and write data to an
external data source, which is an *extended table*. In addition, you might
create one or more internal tables, which are called *collections*.

You can build a variety of formulas that take the name of a table as an
argument, just as a formula in Excel takes one or more cell references
as arguments. Some formulas in Power Apps return a table that reflects
the other arguments that you specify.

**Elements of a table**

![Screenshot showing a column within a table in studio.](../media/column.png)

For the following examples, this table will be assumed to be from a data
source named YourInventory.

**Records**

Each record contains at least one category of information for a person,
a place, or a thing. The example above shows a record for each product
(**Chocolate**, **Bread**, and **Water**) and a column for each category
of information (**Price**, **Quantity on Hand**, and **Quantity on
Order**).

The most common way to retrieve a record from a table is to use the
**LookUp** function. For example, to return the Bread record you would use
the following formula.

```powerappsfl
LookUp(YourInventory, Name = "Bread")
```

This would return the entire record for the Bread product. The **LookUp**
function is covered in detail later in this module.

**Fields**

A *field* is an individual piece of information in a record. You can
visualize this as a value in a column for a record.

As with a control, you refer to a field of a record by using
the decimal (.) operator on the record. For example, **LookUp(YourInventory,Name = "Bread").Price** 
returns the value $ 4.95. You could display
this output in a Label control or use it with other controls or
functions within your app where you need to reference the value.

**Columns**

A *column* refers to the same field for one or more records in a table. In
the above example, each product has a price field, and that price is in
the same column for all products. The above table has four columns,
shown horizontally across the top:

-   **Name**

-   **Price**

-   **Quantity on Hand**

-   **Quantity on Order**

The column's name reflects the fields in that column.

All values within a column are of the same data type. In the above
example, the "Quantity on Hand" column always contains a number and
can't contain a string, such as "12 units," for one record. The value
of any field can also be *blank*.

You might have referred to columns as "fields" in other tools. Sometimes
you need to reference an entire column for a function or control. An
example of this is if you wanted to use the Name column to populate the
choices in a drop-down control. You could reference the Name column by
setting the **Items** property for the drop-down control to
YourInventory.Name. This would then populate the drop-down control with
**Chocolate**, **Bread**, and **Water**. 
