In previous units, you saw that every variable name needs to be enclosed in percentage characters to make the platform interpret it as a variable.

The percentage sign is used as a special character to denote variables. The platform evaluates any expression between percentage as a variable.

![Screenshot of a variable with the percentage notation.](..\media\variables-precentage-notation.png)

If you want to use the percentage sign as a simple character in a hardcoded text,  you have to combine it with the backslash (\\) character.

Power Automate for desktop enables you to create complex expressions containing hardcoded values, variable names, arithmetic operations, comparisons, logical operations, and parentheses.

![Screenshot of an expression with arithmetic and logical operators.](..\media\variables-arithmetic-logical-operations.png)

## Hardcoded values

While developing flows, you might need to include hardcoded text values in expressions. To enter a hardcoded value, you have to use quotes. The flows treat every value between quote characters as a text value rather than a variable name.

![Screenshot of a hardcoded text variable as an action parameter.](..\media\variables-hardcoded-text-values.png)

## Variable names

If you want to use multiple variables in an expression, you can add their names to the expression without any further notation.

![Screenshot of an expression with two variables name.](..\media\variables-multiple-variables.png)

## Basic arithmetic

In case you want to perform mathematical operations, Power Automate for desktop enables you to use all the essential arithmetic operators, such as addition (**+**), subtraction (**-**), multiplication (**\***), and division (**/**).

Except for arithmetic operations with numerical values and variables, you can also use the addition operator to concatenate strings. Adding numbers and text strings in the same expression will convert the numbers into text and join them with the other text strings.

![Screenshot of an expression with arithmetic operator.](..\media\variables-arithmetic-operator.png)

## Comparisons

Besides arithmetic operators, you can also make comparisons using the following relational operators:

| Operator | Description                        |
|--------- |------------------------------------|
| =, !=    | Equal/not equal                    |
| <, <=    | Less than/less than or equal       |
| >, >=    | Greater than/greater than or equal |

![Screenshot of an expression with relational operator.](..\media\variables-relational-operator.png)

> [!NOTE]
> Keep in mind that comparisons produce either **True** or **False** as a value. Naturally, you can perform comparisons exclusively between values of the same type.

## Logical operators

In many flows, you might need to check if a value meets some particular standards. To check conditions and implement more complex logic in a single expression, you can use the logical operators. The supported operators are **AND** and **OR**.

![Screenshot of an expression with logical operator.](..\media\variables-logical-operator.png)

## Parentheses

While creating complex expressions, you might want to prioritize some specific parts of them. To change an operators' priority, use parentheses. Power Automate for desktop handles parentheses the same way as algebra and programming languages.  

![Screenshot of a complex expression with parentheses.](..\media\variables-expressions-parentheses.png)
