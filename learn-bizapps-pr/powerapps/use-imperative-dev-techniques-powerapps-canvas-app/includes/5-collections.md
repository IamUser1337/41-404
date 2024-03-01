In the previous two units, you learned how global and contextual variables store single values. The third variable type, collections, allow you to store a table of data. This is ideal when you need to store large amounts of structured data for reuse in your app. This data can come directly from a data source, can be created within the app, or a combination of both.

## Using collections to increase performance

The most common reason for using collections is to optimize performance by reducing calls to the same table in a data source. For example, if you have a table that stores all of your active projects and you want to reference that list multiple times in your app, then you should consider querying for that data once and storing it in a collection. To store a copy of the **Projects** table from your data source into a collection called **collectProjects**, use the following formula.

```
Collect(collectProjects, Projects)
```

This will create a collection named **collectProjects** that will have the same rows and columns as the **Projects** table from your data source. Here is a couple of considerations that you need to understand about using collections:

-   The Collect function is not delegable. This means by default only
    the first 500 records from the data source will be retrieved and
    stored in the collection. For more information about working with
    delegation, see [Work with data source limits (delegation limits) in a Power Apps canvas app](/training/modules/work-with-data-source-limits-powerapps-canvas-app/?azure-portal=true)

-   Collections are not linked to the data source after you create them.
    This means changes to the data in the collection do not
    automatically save to the data source. This includes changes you have made to the data. If you want to update the
    data source based on your changes to the collection, you will need to
    build formulas to do so, such as recollecting from the data source.

-   Collections are temporary. When you close the app, the collection
    and all of its contents are removed. If you need to store collection
    data, you need to write it to a data source before closing the app.

## Using dynamic collections

Collections do not have to come from a data source. You can also create
a collection from information directly within your app. This is often
done to provide values for a drop-down menu or combo box and to store large
amounts of data before writing to a data source.

Creating a collection with your own data is similar to working with the other variable types. The following formula will create a collection named **collectColors** that matches the structure shown in the following table.

```
Collect(collectColors, {Name: "Shane", FavoriteColor: "Orange"},
{Name: "Mary", FavoriteColor: "Blue"}, {Name: "Oscar", FavoriteColor:
"Yellow"})
```

| Name    | FavoriteColor |
| :-------| :---------------|
| Shane   | Orange |
| Mary    | Blue |
| Oscar   | Yellow |

After you create the collection, you can then reuse it throughout your
app. This also means all of the table functions are available to be
used. The one exception where Collections vary from tabular data sources
is you cannot use them with the Form control.

For more information about working with collections and the table data
they store, see [Author a basic formula that uses tables and records in a Power Apps canvas app](/training/modules/author-basic-formula-tables-records-powerapps/?azure-portal=true).

Additionally, collections store table data no differently than tabular data sources. 
The learning path [Work with data in a Power Apps canvas app](/training/paths/work-with-data-in-a-canvas-app/?azure-portal=true) has many concepts that 
allow you to work with and extend the power of your collections.

In the final unit of this module, you will learn about some additional variable
concepts and how to apply them to your apps.
