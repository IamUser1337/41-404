The **LookUp** function is used to return an individual record of data.
**Lookup** is different from the **Filter** function, which returns one or more
records in a table. Use the **LookUp** function for controls, like the
**Form** control, that need to have a single record specified. Additionally,
you can display a single field from the record, in a control such as a
Label, by using dot "." notation.

For this example, reference the following table of data stored in a
collection named collectCustomerInvoices.

```powerappsfl
ClearCollect(collectCustomerInvoices, {ID:1, Date:"4/10/2020", CustomerName:"Fabrikam", Amount:212.00}, {ID:2, Date:"3/1/2020", CustomerName:"Contoso", Amount:47.89}, {ID:3, Date:"3/14/2020", CustomerName:"Contoso", Amount:32.99},{ID:4, Date:"4/2/2020", CustomerName:"Fabrikam", Amount:105.32}) 
```
<br />

| ID                  | Date                 | CustomerName    | Amount          |
| :-------------------| :------------------- | :---------------| :---------------|
| 1                   | 4/10/2020            | Fabrikam        | 212.00          |
| 2                   | 3/1/2020             | Contoso         | 47.89           |
| 3                   | 3/14/2020            | Contoso         | 32.99           |
| 4                   | 4/2/2020             | Fabrikam        | 105.32          |

To return the record where the Date is 3/14/2020 use the following
formula.

```powerappsfl
LookUp(collectCustomerInvoices, Date = "3/14/2020")
```

This formula will return the first record in the data source that
matches the criteria of date equaling 3/14/2020. An example where you
might use this formula is in the **Item** property of a **Form** control.

Another common use of the **LookUp** function is when you want to
display a field from the record. For example, if you had a data
relationship where you were looking at data for Contoso and you wanted
to return just the amount of the invoice with an ID of 3 in a **Label**
control. You would add a **Label** control and then use the
following formula in the **Text** property to display the amount.

```powerappsfl
LookUp(collectCustomerInvoices, ID =3).Amount
```

This would display in the **Label** control 32.99. This is because the
**LookUp** function returned the entire record where the ID equaled 3. Then
the **.Amount** notation at the end of the function returned the Amount
field for that record.

Every time that you use the **LookUp** function that data source queries for the
record. Looking up a collection is fast because collections are
local to your app. But, if you are looking up a data source
directly, which is common, then making the same query repeatedly
against the database is inefficient.

To avoid repetitive queries, when the data is not going to change, you
can store the record in a variable. Then use the . (dot)-notation to return
the value from the variable. Here's an example:

1.  Add a **Button** control to your app.

2.  Set the following formula for OnSelect for the **Button** control:
    
    ```powerappsfl
    Set(varRecord, LookUp(collectCustomerInvoices, ID =3))
    ```

3.  Add a **Label** control to your app.

4.  Set the following formula for the **Text** property of the **Label**
    control: varRecord.Amount

These steps give you the same result as the previous example, but now
the record is stored in the variable, **varRecord**. You could access
the other properties directly in the same manner. 
