Collections are a special data source. They're local to the app and not backed by a connection to a service in the cloud, so the information can’t be shared across devices for the same user or between users. Collections can be created dynamically with the **Collect** function. They don't need to be established ahead of time, as connection-based data sources do. In other words, collections are just variables, so their contents aren't saved if the user closes the app. Anyone else running the app can't access any data that they contain. To save the information from a collection, we have to write it to a data source. Let's cover two primary ways of saving collection data to your data source.

## Use the Collect function

The **Collect** function adds records to a data source. It's able to add a single value, a record, or a table to a collection. It can be used to create a collection and write to a data source, such as a SharePoint list or a Dataverse table. It enables you to write bulk data *without* using a **ForAll/Patch** function to loop through your data.

When using **Collect** to write to a data source, you can specify the items as a record if the column names, and data structure matches your source. So, something like this formula writes a single record to your data, much like a **Patch** function would:

`Collect('YourDataSource', {Title: 'First Try', StartDate: Today()})`

As long as your data source has columns called 'Title' and 'StartDate' (and they're data types, text and date, respectively) this formula creates a record in your data source where the Title is 'First Try' and the StartDate is today's date.

You could string many records together by adding them after the first record, as long as you're writing the right data type to the right column, including any mandatory columns.  

You could also write an entire table to your data source via the **Collect** statement, again, as long as the data structure matches.

Finally, you can use a simplified version of the formula to write an entire collection to your data source via a syntax such as this:

`Collect('YourDataSource', colMyCollection)`

Just like when we were writing a single record to the data source, when you use **Collect** to write an entire table to your data source, your data structure and column names *must* match for the columns you're writing to. The main advantage in using a **Collect** function for writing is that your code is simple.

In summary, remember these three conditions when using **Collect** to write to your data source:

- The columns in your collection must exist in the data source. The data source can have other columns (such as system-generated columns), but the columns you're writing from in your collection *must* be present in the data source you're writing to. (If your collection has a text column called **Widget**, then your data source must also have a text column called **Widget**.)

- The data type (such as Text, Number, or Date) of each column in the collection must match the destination data type.

- Your collection must include data for any mandatory columns in your data source.

> [!TIP]
> If necessary, you can use functions to transform your collection to match your data source such as:
>
> - AddColumns
> - DropColumns
> - RenameColumns
> - ShowColumns
>
> For more information, see [AddColumns, DropColumns, RenameColumns, and ShowColumns functions in Power Apps.](/power-platform/power-fx/reference/function-table-shaping/?azure-portal=true)

For more information on Collect function and Collections, see [Collect Documentation.](/power-platform/power-fx/reference/function-clear-collect-clearcollect/?azure-portal=true)

## Patch and ForAll

**Patch** is a function that allows you to modify or create a record in your data source. **ForAll** is a function that allows you to run a formula for each record in a table, and collections are tables. You can combine these functions to update your data source with the contents of your collection. Though there's more coding involved versus the **Collect** technique, using a **ForAll/Patch** works best when you want to apply more logic.

For example, you could create a collection named collectColorData that contains three columns: **Name**, **FavoriteColor**, and **UpdateSource**. The **UpdateSource** column could be a Boolean (true or false) column.
Through the process of working with the app, the user would update the value in the column and then select a button that says **Update Source**. You could set the **OnSelect** property for the button to this formula:

```powerappsfl
ForAll(Filter(collectColorData, UpdateSource = true),
Patch(DataSourceName, Defaults(DataSourceName), {NameColumnSource: Name,
FavoriteColorColumnSource: FavoriteColor}))
```

This formula would add new records to the data source named **DataSourceName**, setting the **NameColumnSource** and
**FavoriteColorColumnSource** columns with the values from your collection but *only* for the records where **UpdateSource** was set to true.

This example could be further optimized, but it demonstrates the concept and pieces for dynamically saving your collection to a data source.

For more information on ForAll, see [ForAll Documentation](/power-platform/power-fx/reference/function-forall/?azure-portal=true).

For more information on Patch, see [Patch Documentation](/power-platform/power-fx/reference/function-patch/?azure-portal=true).

Now that we've explored ways we can write data from a collection to a data source, and why we might use one or the other, let's do an exercise where we practice working with external data and collections.
