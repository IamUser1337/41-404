In the previous examples, the tables were only for use in the
current context of the **Data** table or the **Dropdown** control. Often in
your app, you will need to store those tables and use them in multiple
places within the app. To do this, Power Apps has a table variable called
a **collection**.

Collections are a type of variable in Power Apps
-----------------------------------------------

Collections are table variables in which you can store data in a
structured format, as you would in a tabular data source, without
writing to a data source. In other words, they store values in rows and
columns. You can use collections with table functions as you would any
other data source. However, you can't use a collection with the **Form**
control. If you have a developer background, you can think of a
collection as an array. You don't have to initialize or predefine a
collection. When you create it and set values, Power Apps sets it up for
you.

Create a collection
-------------------

Creating a collection can be done within your app anywhere an action can normally be taken. For example, you can create a collection when pressing a button by changing the **OnSelect** property of the button, or even create a collection whenever you come to a certain screen by changing the **OnVisible** property of that screen. You can create a collection named **collectMyFirstCollection** by using
this formula.

```powerappsfl
Collect(collectMyFirstCollection, {Name: "Shane", FavoriteColor:"Orange"})
```

The collection would have a column named **Name** and another column
named **FavoriteColor**. The collection would have one record (row) of
data with Shane as the value of **Name** and Orange as the value for
**FavoriteColor**. Notice the syntax is similar to the **Table**
function from earlier in this module.

You could add another record to the collection by using this formula.

```powerappsfl
Collect(collectMyFirstCollection, {Name: "Nicola", FavoriteColor:"Purple"})
```

You can also add more than one record at a time by using this formula.

```powerappsfl
Collect(collectMyFirstCollection, {Name: "Jeff", FavoriteColor:"Blue"}, {Name: "Chewy", FavoriteColor: "Red"})
```

If you ran all those commands, your collection would look like this
table:

| Name                  | FavoriteColor                 |
| :------------------- | :--------------------|
| Shane  | Orange |
| Nicola                 | Purple                 |
| Jeff                  | Blue                  |
| Chewy                   | Red                   |


You could then use that collection as a data source for your **Gallery** or
**Drop-down** control.

Remove data from your collection
--------------------------------

To clear out the existing data from your collection before you add data,
you can use the **ClearCollect** function. If you take the existing
collection from the previous example, you can use this formula:

```powerappsfl
ClearCollect(collectMyFirstCollection, {Name: "Fausto", FavoriteColor:"Green"})
```

Now your collection would look like this table:

| Name                  | FavoriteColor                 |
| :------------------- | :--------------------|
| Fausto  | Green |

You can also remove all the records from a collection by using the
**Clear** function. This formula removes all the records from your
collection but leaves your columns intact:

```powerappsfl
Clear(collectMyFirstCollection)
``` 
