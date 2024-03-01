Now that you have learned the core concepts of working with tables and
records there are many additional functions you can explore.
These functions work with tables of data so you can use them with a data
source (like Microsoft Dataverse or SharePoint) or a collection. There is no difference
in their usage.

Functions for modifying the data source
---------------------------------------

When it comes to updating a data source, there are two primary functions
to consider:

- **Patch** -- This function is used to either edit an existing
    record or to create a new record in a table. It can write one or
    more fields at a time.

- **Remove** -- This function is used to remove (delete) a
    record from a table.

For example, in your **Gallery** of records, you can add a
**Delete** button. The **Remove** function would provide that functionality.

Functions for getting, rearranging, and counting records
--------------------------------------------------------

Sometimes you want to access a record based on its location instead of
its value. For example, if you wanted to build functionality to get the
invoice number of the last record in the table to display you would use
the **Last** function.

- **First** -- This function returns the first (top) record in
    the table.

- **Last** -- This function returns the last (bottom) record in
    the table.

- **Shuffle** -- This function reorders the records in your
    table in random order.

- **CountRows** -- This function counts the number of
    records in your table.

A fun way to explore these functions is to build a random function for
picking a record from a table. You combine **Shuffle** and **First** to
have a virtual "pick a winner out of a hat". The following example uses
the **collectCustomerInvoices** collection.

```powerappsfl
First(Shuffle(collectCustomerInvoices)).ID
```

Use that formula in the **Text** property of a **Label** control to
display a random ID.

Math functions with tables
--------------------------

In the module, [Author a basic formula to change properties in Power Apps canvas apps](/training/modules/author-basic-formula-change-behaviors-powerapps/?azure-portal=true), you learned about the aggregation functions for
summing, averaging, and other operation on numbers. Now you can apply
that same concept to a table.

For this example, reference the following table of data stored in a
collection named collectCustomerInvoices.

| ID                  | Date                 | CustomerName    | Amount          |
| :-------------------| :------------------- | :---------------| :---------------|
| 1                   | 4/10/2020            | Fabrikam        | 212.00          |
| 2                   | 3/1/2020             | Contoso         | 47.89           |
| 3                   | 3/14/2020            | Contoso         | 32.99           |
| 4                   | 4/2/2020             | Fabrikam        | 105.32          |

1. Place a **Label** control on the screen

2. Set the **Text** property to: Average(collectCustomerInvoices, Amount)

The label will display 99.55 based on the example data. The math
functions are a great way to provide additional information to your
users.
