Your DAX formulas can use operators to create expressions that perform arithmetic calculations, compare values, work with strings, or test conditions.

> [!TIP]
> Many DAX operators and precedence order are the same as those found in Excel.

### Arithmetic operators

The following table lists the arithmetic operators.

|     Operator    |     Description       |
|-----------------|-----------------------|
|     +           |     Addition          |
|     -           |     Subtraction       |
|     *           |     Multiplication    |
|     /           |     Division          |
|     ^           |     Exponentiation    |

Remember, when you are dividing two expressions, and when the denominator could return zero or BLANK, it's more efficient and safer to use the [`DIVIDE`](/dax/divide-function-dax/?azure-portal=true) DAX function.

### Comparison operators

The following table lists the comparison operators, which are used to compare two values. The result is either TRUE or FALSE.

|     Operator    |     Description                   |
|-----------------|-----------------------------------|
|     =           |     Equal to                      |
|     ==          |     Strict equal to             |
|     >           |     Greater than                  |
|     <           |     Less than                     |
|     >=          |     Greater than or equal to    |
|     <=          |     Less than or equal to       |
|     <>          |     Not equal to                  |

All comparison operators, except **strict equal to** (**==**), treat BLANK as equal to the number zero, an empty string (""), the date December 30, 1899, or FALSE. It means that the expression `[Revenue] = 0` will be TRUE when the value of `[Revenue]` is either zero or BLANK. In contrast, `[Revenue] == 0` is TRUE only when the value of `[Revenue]` is zero.

### Text concatenation operator

Use the ampersand (&) character to connect, or concatenate, two text values to produce one continuous text value. For example, consider the following calculated column definition:

```dax
Model Color = 'Product'[Model] & "-" & 'Product'[Color]
```

### Logical operators

Use logical operators to combine expressions that produce a single result. The following table lists all logical operators.

|     Operator              |     Description                                                                                                                                                                                                                |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     &&                    |     Creates an AND condition between two expressions where each has a Boolean result. If both expressions return TRUE, the combination of the expressions also returns TRUE; otherwise the combination returns FALSE. |
|     \|\| (double pipe)    |     Creates an OR condition between two logical expressions. If either expression returns TRUE, the result is TRUE; only when both expressions are FALSE is the result FALSE. |
|     IN                    |     Creates a logical OR condition between each row that is being compared to a table. Note: The table constructor syntax uses braces. |
|     NOT                   |     Inverts the state of a Boolean expression (FALSE to TRUE, and vice versa). |

An example that uses the `IN` logical operator is the **ANZ Revenue** measure definition, which uses the [`CALCULATE`](/dax/calculate-function-dax/?azure-portal=true) DAX function to enforce a specific filter of two countries: Australia and New Zealand.

> [!NOTE]
> You'll be introduced to the powerful `CALCULATE` function when you learn how to modify the filter context.

```dax
ANZ Revenue =
CALCULATE(
    [Revenue],
    Customer[Country-Region] IN {
        "Australia",
        "New Zealand"
    }
)
```

### Operator precedence

When your DAX formula includes multiple operators, DAX uses rules to determine the evaluation order, which is known as an *operator precedence*. Operations are ordered according to the following table.

|     Operator             |     Description                               |
|--------------------------|-----------------------------------------------|
|     ^                    |     Exponentiation                            |
|     -                    |     Sign (as in -1)                         |
|     * and /              |     Multiplication and division             |
|     NOT                  |     NOT                                       |
|     + and -              |     Addition and subtraction                |
|     &                    |     Concatenation of two strings of text    |
|     =,==,<,>,<=,>=,<>    |     Comparison                                |

When the operators have equal precedence value, they're ordered from left to right.

In general, operator precedence is the same as what's found in Excel. If you need to override the evaluation order, then group operations within parentheses.

For example, consider the following calculated column definition:

```dax
Extended Amount = Sales[Order Quantity] * Sales[Unit Price] * 1 - [Unit Price Discount Pct]
```

This sample calculated column definition produces an incorrect result because multiplication happens before the subtraction. The following correct calculated column definition uses parentheses to ensure that the subtractions happen before the multiplications.

```dax
Extended Amount = Sales[Order Quantity] * Sales[Unit Price] * (1 - [Unit Price Discount Pct])
```

> [!TIP]
> Remembering operator precedence rules can be challenging, especially for DAX beginners. Consequently, we recommend that you test your formulas thoroughly. When the formulas don't produce the correct result due to an incorrect evaluation order, you can experiment by adding parentheses to adjust the evaluation order. You can also add parentheses to improve the readability of your formulas.

For more information about DAX operators and precedence order, see [DAX operators](/dax/dax-operator-reference/?azure-portal=true).

### Implicit conversion

When writing a DAX formula that uses operators to combine different data types, you don't need to explicitly convert types. Usually, DAX automatically identifies the data types of referenced model objects and performs implicit conversions where necessary to complete the specified operation.

However, some limitations might exist on the values that can be successfully converted. If a value or a column has a data type that's incompatible with the current operation, DAX returns an error. For example, the attempt to multiply a date value will create an error because it isn't logical.

BLANK is handled differently, depending on the operator that is used. It's handled similar to how Excel treats BLANK, but differently to how databases (SQL) treat NULL. BLANK is treated as zero when acted on by arithmetic operators and as an empty string when concatenated to a string.

> [!TIP]
> Remembering how BLANK is handled can be challenging, especially for DAX beginners. Consequently, we recommend that you test your formulas thoroughly. When BLANKs create unexpected results, consider using the [`IF`](/dax/if-function-dax) and [`ISBLANK`](/dax/isblank-function-dax) DAX functions to test for BLANK, and then respond in an appropriate way.
