When you’re building low-code plug-ins, you would use Microsoft Power Fx to build the logic for what the plug-in does. Building a plug-in with Power Fx is slightly different than building an interactive Power Apps canvas application because the Power Fx logic can't interact with the user or the application user interface. Instant plug-ins get input through parameters that the caller provides, and the plug-ins can provide output in response. Automated plug-ins trigger on a Dataverse data event and receive the data row that triggered the event. Automated plug-ins don't return data. As a result of how plug-ins run, you can’t use the full spectrum of Power Fx formulas in your logic. For example, anything user interface-oriented, such as form-related, device sensor, or visual control specific, isn’t supported in your plug-in logic. This topic covers some unique features of low-code plug-in logic.

## Work with input/output parameters

When building instant plug-ins, you work with parameters in your Power Fx logic. The expression editor helps you by providing IntelliSense that allows you to pick variables as you start typing your expression. This IntelliSense is context sensitive, so if you type a brace (**{**) character, your output variables appear for you to choose from. In other places in the expression, it doesn’t show the output parameters but includes the input parameters for you to reference. The following example shows what the expression would look like when you use an input parameter of MyInput and an output parameter of MyOutput:

```
{MyOutput: "The MyOutput Value " & MyInput}
```

The system returns the output parameters to the invoker of the plug-in by using the Power Fx that uses the [inline records](/power-platform/power-fx/tables/?azure-portal=true) syntax. By using this syntax, you would express records by using braces **{}** that contain named field values. These named field values are your output parameter names.

You can mix your formulas with your output parameters. For example, if you have an input parameter named Score and an output parameter named Valid, you could check Score and then return true or false for Valid.

```
{Valid: If(Score > 500,true,false)}
```

However, you can't embed the output parameters in the If() formula. The following logic isn't valid.

```
If (Score > 500,{Valid:true},{Valid:false})
```

## Use *ThisRecord* with plug-ins

When building automated plug-ins, you don't have input or output parameters, but you can access the Dataverse data row that triggered the event. By using the ThisRecord operator, you can use columns from the triggering data row in your expression. The following logic shows an example of using the First Name column from the triggering data row in the expression.

```
If (StartsWith(ThisRecord.'First Name',"Test"),Error("We don't allow test data"))
```

You can also use the ThisRecord operator with instant plug-in logic when you’re setting up the plug-in scope as an entity. In this case, the invoker of the plug-in is required for you to provide a reference to a data row that’s available to your plug-in logic.

## Reference tables in formulas

If you use a patch() formula, you would typically refer to the table by using its name, such as Accounts. When you use the table in your plug-in logic, use the following disambiguation syntax [@Accounts] by using brackets **[]** and the at **@** symbol.

## Variables

Variables are supported. However, you can't create new variables; you can only use the available ones. 

In automated plug-ins, all columns of the data row that triggered the plug-in to run are available as global variables that you can use with the set() function. For example, if you have an automated plug-in on Contact that’s running pre-operation, you could modify the row's First Name column by using the following logic.

```
Set('First Name',"John")
```

## Use multiple lines in an expression

You can use multiple lines, but you need to make sure that they end with a semi-colon (**;**), except for the last line, as shown in the following example.

```
If(Score < 250,Error("Too Low"));
{Valid: If(Score > 500,true,false), TotalScore:Score+1}
```

When you’re using output parameters that must be the last line in the expression, you can only have one line that contains all output parameters.
