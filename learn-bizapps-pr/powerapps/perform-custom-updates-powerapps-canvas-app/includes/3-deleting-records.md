One topic that has been not covered in previous content is the concept of deleting a record from a tabular data source or collection. Unlike creating and editing records, which have multiple controls and functions, for deleting records there is only the Remove, RemoveIf, and Clear functions. This code is often added to the **OnSelect** property
of a Button or Icon control.

Delete a record
---------------

To delete a record from your data source use the **Remove** function.
Use the **Remove** function to specify the data source and the record that you
want to delete. The most common way to specify this record is to
use the **LookUp** function to retrieve the record from the data source.
Another option is if you are using a Gallery and you want to delete the
current record, the **ThisItem** operator is supported for referencing
the record.

For example, you could use the following formula to delete a record.

```
Remove(CustomerOrders, LookUp(CustomerOrders, ID = 1))
```

This formula will delete the record where the ID equals 1 from the data source **CustomerOrders**.

### Remove doesn't ask to confirm

Remove does not prompt for any confirmation before deleting the
specified record. If you would like to confirm that the user wanted to remove
the record, you would need to create confirmation functionality.

Deleting based on a condition
-----------------------------

If you want to delete more than one record from your data source, you
can use **RemoveIf**. The RemoveIf function allows you to provide a data
source to delete from and a condition for selecting the records to
delete. This is the same logic that is used by the Filter function.

For example, you could use the following formula to delete all of the
records where the Status equals Expired from the **CustomerOrders** data
source.

```
RemoveIf(CustomerOrders, Status = "Expired")
```

Delete all of the records
-------------------------

It is also possible to delete all of the records in a data source. This
is most common with collections where you can use the **Clear**
function. If you want to delete all of the records from a data source,
you can use **RemoveIf**.

### Delete all of the records in a collection

The **Clear** function deletes all the records of a collection. The
columns of the collection will remain. The only input you pass to the
function is the collection name.

For example, you could use the following formula to delete all of the
records from a collection.

```
Clear(collectSelectedItems)
```

This formula will delete all of the records from the
collectSelectedItems collection without changing the columns of the
collection.

You will typically see this type of formula when you want to clear out
the collection without having to redefine it, like in the case of a
reset button or selecting a new order. Note that when working on
collections you also have the **ClearCollect** function.

The **ClearCollect** function deletes all the records from a collection
and then adds a different set of records to the same collection. With a
single function, ClearCollect offers the combination of **Clear** and
then **Collect**.

All three functions have their place. One way to think about whether you
want to use Clear and Collect versus ClearCollect is when the clearing of
the collection happens compared to when you want to add records back.
Here are two examples to illustrate this:

-   All at once - For example, if you are reloading the items in a
    collection for a drop-down menu when a screen becomes visible, you would
    want to use **ClearCollect**. One formula would then remove the old
    records and add the new records.

-   Multi-step - For example, if you are using collections to store
    user inputs like in a shopping cart you can use **Clear**
    and **Collect**. This is because the user might want to clear their
    shopping cart without adding a new record.

### Delete all of the records from a data source

It is possible to delete all of the records from a data source using
**RemoveIf**. This is not a very common scenario. Again there will be no
confirmation before the formula processes unless you build such
functionality. Finally, there is no undo or recycle bin in Power Apps. If
you want to recover your data, you would need to go to your data source
and use whatever recovery process is available for that data source,
outside of Power Apps. Proceed with caution.

For example, you could use the following formula to delete all of the
records from a data source.

```
RemoveIf(CustomerOrders, true)
```

This formula will delete all of the records from the **CustomerOrders** data
source without changing the columns of the data source.

The reason this works is **RemoveIf** checks every record in the data
source to see if the equation equals true. In this case, the equation
has been set to true, so every record will be deleted.

>[!NOTE]
> Setting the equation portion to **true** also works with the
**Filter** function. This can be a valuable setting if you are trying to
troubleshoot formulas where you are not sure if Filter is returning data. 
