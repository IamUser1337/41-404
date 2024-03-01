The DAX function library consists of hundreds of functions, each designed to accomplish a specific goal.

Because DAX originated with the Power Pivot add-in for Microsoft Excel 2010, over 80 functions are available that can also be found in Excel. It was a deliberate design strategy by Microsoft to ensure that Excel users can quickly become productive with DAX.

However, many functions exist that you won't find in Excel because they're specific to data modeling:

- Relationship navigation functions
- Filter context modification functions
- Iterator functions
- Time intelligence functions
- Path functions

> [!TIP]
> To search for documentation that is related to a DAX function, in a web search, enter the keyword *DAX* followed by the function name.

For more information, see the [DAX function reference](/dax/dax-function-reference/?azure-portal=true).

### Functions that originate from Excel

The following sections consider several useful functions that you might already be familiar with because they exist in Excel.

The [`IF`](/dax/if-function-dax/?azure-portal=true) DAX function tests whether a condition that's provided as the first argument is met. It returns one value if the condition is TRUE and returns the other value if the condition is FALSE. The function's syntax is:

```dax
IF(<logical_test>, <value_if_true>[, <value_if_false>])
```

> [!TIP]
> A function argument is optional when documentation shows it enclosed within square brackets.

If **logical_test** evaluates to FALSE and **value_if_false** isn't provided, the function will return BLANK.

Many Excel summarization functions are available, including `SUM`, `COUNT`, `AVERAGE`, `MIN`, `MAX`, and many others. The only difference is that in DAX, you pass in a column reference, whereas in Excel, you pass in a range of cells.

Many Excel mathematic, text, date and time, information, and logical functions are available as well. For example, a small sample of Excel functions that are available in DAX include `ABS`, `ROUND`, `SQRT`, `LEN`, `LEFT`, `RIGHT`, `UPPER`, `DATE`, `YEAR`, `MONTH`, `NOW`, `ISNUMBER`, `TRUE`, `FALSE`, `AND`, `OR`, `NOT`, and `IFERROR`.

### Functions that don't originate from Excel

Two useful DAX functions that aren't specific to modeling and that don't originate from Excel are `DISTINCTCOUNT` and `DIVIDE`.

#### DISTINCTCOUNT function

You can use the [`DISTINCTCOUNT`](/dax/distinctcount-function-dax/?azure-portal=true) DAX function to count the number of distinct values in a column. This function is especially powerful in an analytics solution. Consider that the count of customers is different from the count of *distinct* customers. The latter doesn't count repeat customers, so the difference is "How many customers" compared with "How many *different* customers."

#### DIVIDE function

You can use the [`DIVIDE`](/dax/divide-function-dax/?azure-portal=true) DAX function to achieve division. You must pass in numerator and denominator expressions. Optionally, you can pass in a value that represents an *alternate result*. The `DIVIDE` function's syntax is:

```dax
DIVIDE(<numerator>, <denominator>[, <alternate_result>])
```

The `DIVIDE` function automatically handles division by zero cases. If an alternate result isn't passed in, and the denominator is zero or BLANK, the function returns BLANK. When an alternate result is passed in, it's returned instead of BLANK.

This function is convenient because it saves your expression from having to first test the denominator value. The function is also better optimized for testing the denominator value than the `IF` function. The performance gain is significant because checking for division by zero is expensive. What's more, using the `DIVIDE` function results in a more concise and elegant expression.

> [!TIP]
> We recommend that you use the `DIVIDE` function whenever the denominator is an expression that could return zero or BLANK. In the case that the denominator is a constant value, we recommend that you use the divide operator (/), which is introduced later in this module. In this case, the division is guaranteed to succeed, and your expression will perform better because it will avoid unnecessary testing.
