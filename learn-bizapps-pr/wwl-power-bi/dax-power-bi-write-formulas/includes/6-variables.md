You can declare DAX variables in your formula expressions. When you declare at least one variable, a `RETURN` clause is used to define the expression, which then refers to the variables.

We recommend that you use variables because they offer several benefits:

- Improving the readability and maintenance of your formulas.
- Improving performance because variables are evaluated once and only when or if they're needed.
- Allowing (at design time) straightforward testing of a complex formula by returning the variable of interest.

The following example shows a formula that declares a variable. The **Revenue YoY %** measure definition is rewritten to declare a variable that's assigned the value of the prior year's revenue.

```dax
Revenue YoY % =
VAR RevenuePriorYear =
    CALCULATE(
        [Revenue],
        SAMEPERIODLASTYEAR('Date'[Date])
    )
RETURN
    DIVIDE(
        [Revenue] - RevenuePriorYear,
        RevenuePriorYear
    )
```

Notice that the `RETURN` clause refers to the variable twice. This improved measure definition formula will run in at least half the time because it doesn't need to evaluate the prior year's revenue twice.

In the [**Adventure Works DW 2020 M02.pbix**](https://github.com/MicrosoftDocs/mslearn-dax-power-bi/raw/main/activities/Adventure%20Works%20DW%202020%20M02.pbix) Power BI Desktop file, refactor the **Revenue YoY %** measure to produce the same result as the previous example.

For more information on using DAX variables, see [Use variables to improve your formulas](/power-bi/guidance/dax-variables/?azure-portal=true).
