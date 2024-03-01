You can use variables in your DAX formulas to help you write less complex and more efficient calculations. Variables are underused by developers who are starting out in Power BI Desktop, but they are effective and you should use them by default when you are creating measures.

Some expressions involve the use of many nested functions and the reuse of expression logic. These expressions take a longer time to process and are difficult to read and, therefore, troubleshoot. If you use variables, you can save query processing time. This change is a step in the right direction toward optimizing the performance of a semantic model.

The use of variables in your semantic model provides the following advantages:

-   **Improved performance** - Variables can make measures more efficient because they remove the need for Power BI to evaluate the same expression multiple times. You can achieve the same results in a query in about half the original processing time.

-   **Improved readability** - Variables have short, self-describing names and are used in place of an ambiguous, multi-worded expression. You might find it easier to read and understand the formulas when variables are used.

-   **Simplified debugging** - You can use variables to debug a formula and test expressions, which can be helpful during troubleshooting.

-   **Reduced complexity** - Variables do not require the use of EARLIER or EARLIEST DAX functions, which are difficult to understand. These functions were required before variables were introduced, and were written in complex expressions that introduced new filter contexts. Now that you can use variables instead of those functions, you can write fewer complex formulas.

## Use variables to improve performance

To illustrate how you can use a variable to make a measure more efficient, the following table displays a measure definition in two different ways. Notice that the formula repeats the expression that calculates "same period last year" but in two different ways: the first instance uses the normal DAX calculation method and the second one uses variables in the calculation.

The second row of the table shows the improved measure definition. This definition uses the VAR keyword to introduce a variable named **SalesPriorYear**, and it uses an expression to assign the "same period last year" result to that new variable. It then uses the variable twice in the DIVIDE expression.

**Without variable**

```DAX
Sales YoY Growth =
DIVIDE (
    ( [Sales] - CALCULATE ( [Sales], PARALLELPERIOD ( 'Date'[Date], -12, MONTH ) ) ),
    CALCULATE ( [Sales], PARALLELPERIOD ( 'Date'[Date], -12, MONTH ) )
)
```

**With variable**

```DAX
Sales YoY Growth =
VAR SalesPriorYear =
    CALCULATE ( [Sales], PARALLELPERIOD ( 'Date'[Date], -12, MONTH ) )
VAR SalesVariance =
    DIVIDE ( ( [Sales] - SalesPriorYear ), SalesPriorYear )
RETURN
    SalesVariance
```

In the first measure definition in the table, the formula is inefficient because it requires Power BI to evaluate the same expression twice. The second definition is more efficient because, due to the variable, Power BI only needs to evaluate the PARALLELPERIOD expression once.

If your semantic model has multiple queries with multiple measures, the use of variables could cut the overall query processing time in half and improve the overall performance of the semantic model. Furthermore, this solution is a simple one; imagine the savings as the formulas get more complicated, for instance, when you are dealing with percentages and running totals.

## Use variables to improve readability

In addition to improved performance, you might notice how the use of variables makes the code simpler to read.

When using variables, it is best practice to use descriptive names for the variables. In the previous example, the variable is called **SalesPriorYear**, which clearly states what the variable is calculating. Consider the outcome of using a variable that was called **X**, **temp** or **variable1**; the purpose of the variable would not be clear at all.

Using clear, concise, meaningful names will help make it easier for you to understand what you are trying to calculate, and it will be much simpler for other developers to maintain the report in the future.

## Use variables to troubleshoot multiple steps

You can use variables to help you debug a formula and identify what the issue is. Variables help simplify the task of troubleshooting your DAX calculation by evaluating each variable separately and by recalling them after the RETURN expression.

In the following example, you test an expression that is assigned to a variable. In order to debug you temporarily rewrite the RETURN expression to write to the variable. The measure definition returns only the **SalesPriorYear** variable because that is what comes after the RETURN expression.
```DAX
Sales YoY Growth % =
VAR SalesPriorYear =  CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
VAR SalesPriorYear% = DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)  
RETURN  SalesPriorYear%
```

The RETURN expression will display the **SalesPriorYear%** value only. This technique allows you to revert the expression when you have completed the debugging. It also makes calculations simpler to understand due to reduced complexity of the DAX code.
