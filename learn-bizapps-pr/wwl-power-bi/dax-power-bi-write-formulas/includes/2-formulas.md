Each model calculation type, calculated table, calculated column, or measure is defined by its name, followed by the equals symbol (=), which is then followed by a DAX formula. Use the following template to create a model calculation:

```dax
<Calculation name> = <DAX formula>
```

For example, the definition of the **Ship Date** calculated table that duplicates the **Date** table data is:

```dax
Ship Date = 'Date'
```

A DAX formula consists of expressions that return a result. The result is either a table object or a scalar value. Calculated table formulas must return a table object; calculated column and measure formulas must return a scalar value (single value).

Formulas are assembled by using:

- DAX functions
- DAX operators
- References to model objects
- Constant values, like the number 24 or the literal text "FY" (abbreviation for fiscal year)
- DAX variables
- Whitespace

> [!TIP]
> When entering DAX formulas in Power BI Desktop, you have the benefit of *IntelliSense*. IntelliSense is a code-completion aid that lists functions and model resources. When you select a DAX function, it also provides you with a definition and description. We recommend that you use IntelliSense to help you quickly build accurate formulas.

## DAX functions

Similar to Microsoft Excel, DAX is a functional language meaning that formulas rely on functions to accomplish specific goals. Typically, DAX functions have arguments that allow passing in variables. Formulas can use many function calls and will often nest functions within other functions.

In a formula, function names must be followed by parentheses. Within the parentheses, variables are passed in.

> [!NOTE]
> Some functions don't take arguments, or arguments might be optional.

Working with DAX functions is described later in this module.

## DAX operators

Formulas also rely on operators, which can perform arithmetic calculations, compare values, work with strings, or test conditions.

DAX operators are described in more detail later in this module.

## References to model objects

Formulas can only refer to three types of model objects: tables, columns, or measures. A formula can't refer to a hierarchy or a hierarchy level. (Recall that a hierarchy level is based on a column, so your formula can refer to a hierarchy level's column.)

### Table references

When you reference a table in a formula, officially, the table name is enclosed within single quotation marks. In the following calculated table definition, notice that the **Date** table is enclosed within single quotation marks.

```dax
Ship Date = 'Date'
```

However, single quotation marks can be omitted when both of the following conditions are true:

1. The table name does not include embedded spaces.
1. The table name isn't a reserved word that's used by DAX. All DAX function names and operators are reserved words. *Date* is a DAX function name, which explains why, when you are referencing a table named **Date**, that you must enclose it within single quotation marks.

In the following calculated table definition, it's possible to omit the single quotation marks when referencing the **Airport** table:

```dax
Arrival Airport = Airport
```

### Column references

When you reference a column in a formula, the column name must be enclosed within square brackets. Optionally, it can be preceded by its table name. For example, the following measure definition refers to the **Sales Amount** column.

```dax
Revenue = SUM([Sales Amount])
```

Because column names are unique within a table but not necessarily unique within the model, you can disambiguate the column reference by preceding it with its table name. This disambiguated column is known as a *fully qualified column*. Some DAX functions require passing in fully qualified columns.

> [!TIP]
> To improve the readability of your formulas, we recommend that you always precede a column reference with its table name.

The previous example measure definition can be rewritten as:

```dax
Revenue = SUM(Sales[Sales Amount])
```

### Measure references

When you reference a measure in a formula, like column name references, the measure name must be enclosed within square brackets. For example, the following measure definition refers to the **Revenue** and **Cost** measures.

```dax
Profit = [Revenue] - [Cost]
```

If you're a DAX beginner, the fact that column and measure references are always enclosed within square brackets can cause confusion when you're trying to read a formula. However, as you become proficient with DAX fundamentals, you'll be able to determine which type of object it is because, in DAX formulas, columns, and measures are used in different ways.

> [!TIP]
> It's possible to precede a measure reference with its table name. However, measures are a model-level object. While they're assigned to a home table, it's only a cosmetic relationship to logically organize measures in the **Fields** pane.
>
> Therefore, while we recommend that you always precede a column reference with its table name, the inverse is true for measures: We recommend that you never precede a measure reference with its table name.
>
> For more information, see [Column and measure references](/power-bi/guidance/dax-column-measure-references/?azure-portal=true).

## DAX variables

Formulas can declare DAX variables to store results.

How and when to use DAX variables is described later in this module.

## Whitespace

Whitespace refers to characters that you can use to format your formulas in a way that's quick and simple to understand. Whitespace characters include:

- Spaces
- Tabs
- Carriage returns

Whitespace is optional and it doesn't modify your formula logic or negatively impact performance. We strongly recommend that you adopt a format style and apply it consistently, and consider the following recommendations:

- Use spaces between operators.
- Use tabs to indent nested function calls.
- Use carriage returns to separate function arguments, especially when it's too long to fit on a single line. Formatting in this way makes it simpler to troubleshoot, especially when the formula is missing a parenthesis.
- Err on the side of too much whitespace than too little.

> [!TIP]
> In the formula bar, to enter a carriage return, press **Shift+Enter**. Pressing **Enter** alone will commit your formula.

Consider the following measure definition that's written in a single line and that includes five DAX function calls:

```dax
Revenue YoY % = DIVIDE([Revenue] - CALCULATE([Revenue], SAMEPERIODLASTYEAR('Date'[Date])), CALCULATE([Revenue], SAMEPERIODLASTYEAR('Date'[Date])))
```

The following example is the same measure definition but now formatted, which helps make it easier to read and understand:

```dax
Revenue YoY % =
DIVIDE(
    [Revenue]
        - CALCULATE(
            [Revenue],
            SAMEPERIODLASTYEAR('Date'[Date])
    ),
    CALCULATE(
        [Revenue],
        SAMEPERIODLASTYEAR('Date'[Date])
    )
)
```

Try formatting the measure on your own. Open the [**Adventure Works DW 2020 M02.pbix**](https://github.com/MicrosoftDocs/mslearn-dax-power-bi/raw/main/activities/Adventure%20Works%20DW%202020%20M02.pbix) Power BI Desktop file and then, in the **Fields** pane, expand the **Sales** table and then select the **Revenue YoY %** measure. In the formula bar, use tab and carriage return characters to produce the same result as the previous example. When you add a carriage return, remember to press **Shift+Enter**.

This measure definition can be further improved for readability and performance, which will be explained later in this module.

> [!TIP]
> An excellent formatting tool from another source that can help you format your calculations is [DAX Formatter](http://www.daxformatter.com/?azure-portal=true). This tool allows you to paste in your calculation and format it. You can then copy the formatted calculation to the clipboard and paste it back into Power BI Desktop.
