When you are working with tables of data, it is common to want to
return a subset of the records instead of the entire table. For example,
you can filter all the customer records where the status is
active or all of the invoices where the date is older than 30 days ago.
To accomplish this in Power Apps, you can use the **Filter** function.

The **Filter** function in Power Apps allows you to query a table of data
(which could come from a collection or a data source) for the records
that match the evaluation criteria.

For this example, reference the following Table of data stored in a
collection named collectCustomerInvoices.

| ID                  | Date                 | CustomerName    | Amount          |
| :-------------------| :------------------- | :---------------| :---------------|
| 1                   | 4/10/2020            | Fabrikam        | 212.00          |
| 2                   | 3/1/2020             | Contoso         | 47.89           |
| 3                   | 3/14/2020            | Contoso         | 32.99           |
| 4                   | 4/2/2020             | Fabrikam        | 105.32          |

Use the following filter formula to return all of the records where the
**CustomerName** field is Contoso.

```powerappsfl
Filter(collectCustomerInvoices, CustomerName = "Contoso")
```

The formula would return a table that contained the second and third
records only. You can use this method to reduce the amount of data
displayed in your app. This makes for a better user experience
and better performance. For more information and to see
other uses of the **Filter** function,
see [Filter, Search, and LookUp functions in Power Apps](/power-apps/maker/canvas-apps/functions/function-filter-lookup/?azure-portal=true).
