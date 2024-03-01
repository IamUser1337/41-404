When working with data sometimes, you need to be able to modify the data. Common scenarios include taking a table of records and combining the records into one string to display or taking a string and turning it into multiple records in a table. With
Power Apps you use the **Concat** and **Split** functions to accomplish
this task.

## Turn table data into a string

The **Concat** function combines the result of a formula applied across
all the records of a table, resulting in a single string. Use this
function to summarize the strings of a table, just as the **Sum**
function does for numbers. This could be used to create a list of comma-separated values to display all of the customers assigned to a sales
rep, a semicolon-separated list of email addresses to pass to an email
function, or to dynamically generate an HTML table to be used in the
creation of a PDF document with the help of Power Automate.

Fields of the record currently being processed are available within the
formula. You simply reference them by name as you would any other value.
You can also reference control properties and other values throughout your app.

For example, you could use Concat(CustomerOrders, Email & ";") to create
a single string that contains the values of the Email column separated
by a semicolon. You could use this formula for the To: argument in the
Office365.SendEmail function to send a single email to all of those
addresses.

> [!div class="mx-imgBorder"]
> [![Screenshot of the the Concat code and the resulting expression.](../media/concat-example.png)](../media/concat-example.png)

As you begin using the **Concat** function be sure not to confuse it with
the
[**Concatenate**](/power-apps/maker/canvas-apps/functions/function-concatenate/?azure-portal=true)
function that is used to combine multiple strings into one string.

## Turn a string into a single column table

The **Split** function breaks a text string into a table of substrings.
Use the **Split** function to break up comma-delimited lists, dates that
use a slash between date parts, to break a word into the individual
characters, and in other situations where you need a well-defined
delimiter.

A separator string is used to break the text string apart. The separator
can be zero, one, or more characters that are matched as a whole in the
text string. Using a zero length or blank separator results in each
character being broken out individually. The matched separator
characters aren’t returned in the result. If no separator match is found, then the entire text string is returned as a single result.

For example, you could use Split("Canada, Mexico, United States of
America", ",") to create a single column table with three records. The
name of the column would be Result. This can be useful when retrieving
data from a multi-value field and you want to use those values in a
drop-down control. In this example, you would set the Items property of
the drop-down control with the formula.

In the next unit, you’ll learn how to process a formula once for every
record in a table. 
