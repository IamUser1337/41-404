In the realm of business applications, precision in data presentation is crucial. To achieve this, utilize functions like Filter and Search. By delegating these functions to the data source for processing, you streamline the information flow.

Delegation here means that these functions act as selective filters on the server side. The outcome? Your application selectively fetches and processes only the necessary data, enhancing the user experience. This approach not only reduces data transmission but also optimizes efficiency for your users.

In the previous module, you learned about adding a data source to a gallery.
In this module, you expand on those concepts by shaping the data to show
what is relevant to the user.

Use the filter function to filter data
----------------

The Filter function is the most commonly used function for shaping data.
With Filter, you can create simple queries that allow you to return only
the data you need. For example, if your data source has a text column
named **IsActive** with **Yes** or **No** values for tracking project
status, you could filter your data by using the following formula in the
Items property of your gallery.

```powerappsfl
Filter(YourDataSourcetable, IsActive = "Yes")
```

Instead of displaying all of the rows from the table, the
gallery would only show the rows that had Yes in the column IsActive.
This gives your users fewer rows to sort through and speeds up the
app by reducing the amount of data downloaded.

And operator
----------------

Taking filtering to the next level involves employing operators to create more intricate filters. One commonly used method is employing the And operator to merge multiple criteria within the filter. When employing the And operator, all conditions must evaluate to true for the filter to be effective. For example, you could extend the previous
example to show all of the rows where **IsActive** is **Yes** and
**Region** is **North** by using the following query.

```powerappsfl
Filter(YourDataSourcetable, IsActive = "Yes" And Region = "North")
```

This formula returns all of the rows where IsActive is Yes, and
the Region is North. Note, when using the And operator in your formula,
it must be capitalized.

Or operator
---------------

Introducing another essential operator for filters: the Or operator. Unlike the And operator, the Or operator requires only one equation to be true to retrieve the row. Similar to the And operator, it's important to capitalize the Or operator for it to function correctly within the filter criteria.

Expanding on the previous example, there might be a case where you want to
see all rows where the Region is North or West. To build that query, you would use the Or operator.

```powerappsfl
Filter(YourDataSourcetable, Region = "North" Or Region = "West")
```

This formula returns all of the rows where Region is equal to
North or West. Also, note the syntax in the formula: Region =
"North" Or Region = "West". A common mistake is to write Region =
"North" Or "West". That is an incorrect formula.

Combining operators
-------------------

In scenarios demanding complex conditions, combining operators allows for more sophisticated logic. Consider the earlier examples: imagine a scenario where you aim to filter your data source to retrieve rows where IsActive is Yes, and the Region is either North or West.

To accomplish this, incorporating parentheses in your formula becomes essential. Here's how your formula would look:

```powerappsfl
Filter(YourDataSourcetable, IsActive = "Yes" And (Region = "North" Or Region = "West"))
```

The formula evaluates the parentheses first. In this formula, it
first determines if the Region is North or West. If either of those
evaluations is true, then the right side is true. Next, the formula
checks the value of the IsActive column. If that equals "Yes," then
the row is a match and the Filter function returns it.
Microsoft Power Apps supports a wide range of operators and the nesting of them to
shape your data.

For more information on the different operators that are available in
Power Apps, see [Operators and data types in Power Apps](/power-apps/maker/canvas-apps/functions/operators/?azure-portal=true)
in the documentation. Other examples include greater
than, less than, not, in, exact in, and more. Also, when evaluating
operators be sure that you understand delegation. Different operators have
different delegation behaviors with different data sources. For a list
of data sources and their operators,
see [Understand delegation in a canvas app](/power-apps/maker/canvas-apps/delegation-list/?azure-portal=true).
