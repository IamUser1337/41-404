Semantic model columns have a set data type, which ensures that all column values conform to that data type. Column data types are defined in Power Query, or in the case of calculated columns, it's inferred from the formula. Measure data types, similar to calculated column data types, are inferred from the formula.

Model data types aren't the same as DAX data types, though a direct relationship exists between them. The following table lists the model data types and DAX data types. Notice the supported range of values for each data type.

|     Model data type    |     DAX data type     |     Description                                                                                                                                  |
|------------------------|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|     Whole number       |     64-bit integer    |     -2<sup>63</sup> through 2<sup>63</sup>-1 |
|     Decimal number     |     64-bit   real     |     Negative: -1.79 x 10<sup>308</sup> through -2.23 x 10<sup>-308</sup> - zero (0) - positive: 2.23 x 10<sup>-308</sup> through 1.79 x 10<sup>308</sup> - Limited to 17 decimal digits |
|     Boolean            |     Boolean           |     TRUE or FALSE |
|     Text               |     String            |     Unicode character string |
|     Date               |     Date/time         |     Valid dates are all dates after January 1, 1900 |
|     Currency           |     Currency          |     -9.22 x 10<sup>14</sup> through 9.22 x 10<sup>14</sup> - limited to four decimal digits of fixed precision |
|     N/A                |     BLANK             |     In some cases, it's the equivalent of a database (SQL) NULL |

## BLANK data type

The BLANK data type deserves a special mention. DAX uses BLANK for both database NULL and for blank cells in Excel. BLANK doesn't mean zero. Perhaps it might be simpler to think of it as the *absence of a value*.

Two DAX functions are related to the BLANK data type: the [`BLANK`](/dax/blank-function-dax/?azure-portal=true) DAX function returns BLANK, while the [`ISBLANK`](/dax/isblank-function-dax/?azure-portal=true) DAX function tests whether an expression evaluates to BLANK.
