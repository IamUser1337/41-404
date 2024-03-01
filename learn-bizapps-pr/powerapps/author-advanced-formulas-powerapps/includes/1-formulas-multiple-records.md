Throughout other Power Apps learning paths, you’ve been focused on using formulas to manipulate single records. That is a great way to get started with Power Apps. As you build more complex apps, it’s often necessary to process and work with multiple records in one formula. Throughout this module, the focus will be on learning some of the more common functions that are used to work with tables, records, and collections.
To keep the rest of this module straightforward, the content will refer to tables and records. *Tables* are a data set that is made up of one or more columns with one or more rows of data. A *record* is the name used to refer to the individual rows in the table. Tables can be manually created using the Table function or come from a tabular data source. Collections are a special kind of variable that stores a table. Throughout this module, table and collection are synonymous. This means that any function you can use on a table of data, you can use on a collection.


## Calculations based on multiple records

Sometimes the functions aren’t about changing the table but performing
math operations in relation to the data. The most basic is the
**CountRows** function. This simple function is used to count the number
of rows (records) in a table. There are also more traditional math
functions such as **Sum** or **Average**. These functions process a
numerical operation over a table of data. We’ll explore this some more in the next unit.

## Splitting up and combining data

When working with your data, it’s often necessary to transform the data
to display it or sort it properly. For example, you can’t
display a record in a label. To change those records into a
comma-separated list of data you can use the **Concat** function. The
function allows you to specify a formula to process over a table of data
and the result of each record is separated by a string you specify. The
reverse of this is also possible with the **Split** function. You can
use the **Split** function to take a string that is separated by a
character, like a comma, and turn it into a table of data. Both
functions open up possibilities for working with data the way you
want.

## Taking action across a table of data

There might be situations where you want to process your data in ways with no available built-in function. In this instance, you can use  the **ForAll** function. ForAll is a dynamic function
that allows you to run a formula once for each record in a table while
referencing all of the data in the current record. For example, if you
wanted to send an individual email to every customer in your table, a
ForAll function could run the Office365.SendEmail function once for each
customer.

## Tables are flexible

As you work through this module, remember that all of the functions are about working with a table of data. This includes tables that you create with the Table function, tables that come from tabular data sources, collections, and formulas that output tables. Functions like Filter and Search output a table of data and you can use functions with that table of data. For example, you might use Sum(CustomerEntity, InvoiceAmount) to calculate the total amount of invoices in the table. But, you could also filter the data where you only sum the customers where Country equals Germany by modifying the formula to Sum(Filter(CustomerEntity, Country = "Germany"), InvoiceAmount). This concept applies to all of the functions throughout this module.
In the next unit, you’ll learn how to use math operations across tables.


