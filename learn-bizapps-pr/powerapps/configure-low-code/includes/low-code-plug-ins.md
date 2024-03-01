Dataverse low-code plug-ins help makers centralize Power Fx logic and run it on demand or in response to a Dataverse table event. With low-code plug-ins, makers can use Power Fx for something that was previously only possible by using traditional .NET coding.

You can create low-code plug-ins to help solve two common problems that might occur when you’re building an application or automation:

-	When making a Microsoft Power Apps canvas app, you can repeat the same Power Fx expressions multiple times within a single app or across various apps. This duplication creates a maintenance challenge because, if you need to update the logic, you need to update it in multiple places.

 	 By creating a low-code plug-in, you can centralize your Power Fx logic and reuse it from multiple Power Apps applications or Microsoft Power Automate flows.

-	When you place your logic inside an application or flow that creates or updates a table row, the logic only runs when the application or flow creates or updates the table row. If someone builds a new application or flow and then forgets to add the same logic, it doesn't run. Cosequently, your data isn't processed by a consistent set of rules.

    By creating a plug-in that runs on a table event, such as when someone creates or updates a row, your logic always runs, regardless of the application or flow that creates or modifies the data.

## On-demand plug-ins

On-demand plug-ins only run when you invoke them from a Power Apps expression or a Power Automate flow step. This type of plug-in is called an instant plug-in. It's instant because it runs the Power Fx logic immediately and gives you the results when you invoke it.

When you create an instant plug-in, you can provide input parameters that allow you to pass data into the plug-in. Your Power Fx logic can use these parameters. The parameters help make your plug-in Power Fx logic independent from the app that's invoking the plug-in. You can also define output parameters to allow your Power Fx logic to return values to the invoker of the instant plug-in.

For example, consider a scenario where you have account numbers, and you want to validate whether the account number value is valid or not. For the purpose of this example, assume that correct account numbers must start with two alphabetical (A-Z) characters followed by a four-digit number. Therefore, account **AA9999** would be valid, and account **A999CCC** would be invalid.

To implement this example as a low-code plug-in, you would create an instant plug-in named **IsValidAccountNumber**. Then, you would define one input parameter of AccountNumber as a string data type. You would use Power Fx formulas to evaluate the contents of AccountNumber to determine if it's invalid. Next, you would define an output parameter named Valid of type Boolean to inform the caller if it’s valid. The expression would resemble the following example plug-in logic:

```powerappsfl
{Valid: IsMatch(AccountNumber,"^[A-Za-z]{2}\d{4}$")}
```

Many apps and flows could reuse this data validation logic, and you would use the same logic every time. Each app or flow could have the flexibility to determine when to call it and how to handle it if the account number is invalid.

## Automated plug-ins

Automated plug-ins are always tied to a Dataverse table row event, such as create, update, or delete. Dataverse runs this plug-in type when the event occurs. No application or flow controls it. Unlike an instant plug-in, where you can provide the input parameters, automated plug-ins only have a single parameter, the data row, which is the event's target.

Similar to the previous example, consider a scenario where you want to ensure that the Account Number column on any Service Request table row is valid. If the column isn't valid, you don't want to allow the change to happen.

To implement this scenario, you would create an automated plug-in and then associate it with the create and update operations of the Service Request Dataverse table. Your logic would check the Account Number value, and if it isn't valid, you would raise an error that stops the Dataverse operation from completing. The expression for the plug-in would resemble the following example logic:

```powerappsfl
If(!IsMatch(ThisRecord.contoso_accountnumber,"^[A-Za-z]{2}\d{4}$"), Error({ Kind: ErrorKind.Validation , Message: "Account number must be 6 characters that start with two letters followed by 4 digits" }))
```

This data validation logic always runs, regardless of whether you create or update the row from an app, flow, copilot, or by using the Dataverse API from traditional code. This separation makes automated plug-ins an excellent choice to ensure that your logic consistently runs.
