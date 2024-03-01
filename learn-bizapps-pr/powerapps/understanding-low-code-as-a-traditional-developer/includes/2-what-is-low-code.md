## What is low code, and how is it used in canvas-based Power Apps?

You and Kiana have worked on the same "high code" or traditional development team at VanArsdel for a long time. You've developed everything from .NET Core Console applications to ASP.NET Core web APIs to reusable libraries shared via NuGet together. As you sit down to learn Power Apps from a traditional development background, it helps to understand what is meant by "low code".

The term "low code" can mean different things to different people when they first hear it. What we mean when we talk about low code is that with tools like Power Apps, you only need to write a small amount of code to get results that would normally take several more lines of code in a traditional programming language.

In canvas-based Power Apps, the low code scripting language used is called [Power Fx](/power-platform/power-fx/overview/?azure-portal=true); that is the language we will be learning and using throughout this module to build our app.

Take this as an example: to look up the first name of the employee for an order, one would write the Power Fx formula or equivalent JavaScript as seen in the animation below. This animation shows the mapping between the parts of the Power Fx formula and the concepts that need to be explicitly coded in the equivalent JavaScript.

![Power Fx and JavaScript comparison](../media/powerfx-vs-javascript-example.gif)

Let’s look more in depth at all the things that Power Fx is doing for us and the freedom it has to optimize because the formula was declarative:

### Asynchronous

All data operations in Power Fx are asynchronous. The developer doesn’t need to specify this, nor does the developer need to synchronize after the call is over. Most importantly, the developer doesn’t need to be aware of this concept at all, they don’t need to know what a promise or lambda function is.

### Local and remote

Power Fx uses the same syntax and functions for data that is local in-memory and remote in a database or service. The user need not think about this distinction. Power Fx automatically delegates what it can to the server to process filters and sorts there more efficiently.

### Relational data

Orders and Customers are two different tables, related through a many-to-one relationship. The OData query requires an “$expand” with knowledge of the foreign key, similar to a Join in SQL. The formula has none of this, in fact database keys are another concept the maker doesn’t need to know about. The maker can use simple dot notation to access the entire graph of relationships from a record.

### Projection

When writing a query, many developers will write “select * from …” that brings back all the columns of data. Power Fx does analysis of all the columns that are used through the entire app, even across formula dependencies. Projection is automatically optimized and again the maker need not even know what that word means.

### Retrieve only what is needed

In this example, the LookUp function implies that only one record should be retrieved and that is all that is brought back. If more records are requested by using the Filter function, for which thousands of records may qualify, only a single page of data is brought back at a time, on the order of a hundred records. The user must gesture through a gallery or data table to see the additional data, and it is automatically brought in for them. The maker can reason about large sets of data without needing to think about limiting data requests to reasonable chunks.

### Runs only when is needed

We defined a formula for the Text property of the label control. As the variable Selected changes, the LookUp is automatically recalculated and the label updated. The maker did not need to write an OnChange handler for Selection, needing to remember that this label is dependent upon it. This is declarative programming as discussed earlier; the maker specified what they wanted to have in the label, not how or when it should be fetched. In fact, if this label is not visible because it is on a screen that is not visible or its Visible property is false, we can defer this calculation until the label is visible and effectively eliminate it if that rarely happens.

### Excel syntax translation

Excel is used by hundreds of millions of users, most of which know that “&” is used for string concatenation. JavaScript uses “+” and other languages use “.”. Power Fx is meeting makers where they are, leveraging the knowledge they already have.

### Display names and localization

'First Name' is used in the Power Fx formula while nwind_firstname is used in the JavaScript equivalent. In [Dataverse](/power-apps/maker/data-platform/?azure-portal=true) and SharePoint, there is a display name for fields and tables as well as a unique logical name. The display names are often much more user friendly, as in this case, but they have another important quality: they can be localized. If you have a multi-lingual team, each team member can see table and field names in their own language. In all cases, Power Fx makes sure that the correct logical name is sent to the database automatically.

### Always live

There is another Excel trait that is critical for citizen developers: immediate feedback. If you stop to think about it, Excel has no edit mode, compile step, or run state. What’s great is that you’ve probably never thought about that before: you load your spreadsheet, you edit formulas and values freely, and you get your answers. The spreadsheet is always live while in Excel and there is no distinction made between editing and running. Changes in any value or formula are immediately propagated throughout the spreadsheet and the maker can quickly check for the right answer. Any errors that Excel detects are surfaced immediately and don’t interfere with the rest of the spreadsheet.
