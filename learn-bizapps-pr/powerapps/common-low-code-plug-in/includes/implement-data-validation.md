You can use low-code plug-ins for centralizing your data validation logic. By using plug-ins, you can ensure that the logic is always run, regardless of how users work with the data. You can use instant plug-ins to allow the validation logic to run on demand. Additionally, you can use automated plug-ins to run the logic whenever data changes.

## Use instant plug-ins

When using instant plug-ins, you can use the error function or output parameters to communicate with the caller of the instant plug-in action. By using output parameters, you can provide the caller with a more graceful experience in handling the error than you can with the error function. For example, you could write a Boolean indicator if the data is valid and a message parameter that provides more details on what’s wrong if it isn't valid.

## Use automated plug-ins

When you’re using automated plug-ins, the primary way of communicating a problem is by using the error function. Alternatively, you can modify the data row to indicate a problem. The main difference in the approaches is that, when you use the error function in an automated plug-in, any work that your plug-in or the original request does is terminated and data changes are rolled back. For example, if the user creates a contact, and you find a problem in an address validation plug-in, then you would use the error function. In this example, the user would notice the error and then wouldn’t add the contact to Dataverse. This approach works well to prevent bad data from being stored, but it might not be the most user-friendly experience. By using the modify data row approach, you could add an address valid indicator on the data row, and then the plug-in could modify this indicator with the data validation results. With this approach, the user is still able to save the contact but can use the indicator to trigger a follow-up business process to clean up the invalid data.

When you’re using automated plug-ins for validation, make sure that you set up the plug-in to run during pre-operation. This option is the most efficient because, if a problem occurs, the system stops the operation before updating Dataverse and then it completes a rollback on any completed work.

## Use Power Fx for validating data

Power Fx has many functions that can be helpful when you’re composing validation logic. The following functions are a few that you should become familiar with.

- **DateDiff** - This function can be useful when you’re working with dates to determine if they're out of a valid range. For example, you want to make sure the service request date isn't over 90 days in the future.

- **StartsWith, EndsWith** - This function can be useful for checking contents of a string for specific data.

- **IsBlank, IsEmpty** - You can use IsBlank to check if a column has data, such as whether First Name and Last Name contain data. You can use IsEmpty to check if a table is empty. For example, if you want to know if any existing Contact rows have a specific name, you would use the filter and check the results by using IsEmpty.

- **IsMatch,Match, and MatchAll** -  The match functions are powerful because they allow you to match against a pattern or [regular expression](/power-platform/power-fx/reference/function-ismatch?azure-portal=true#regular-expressions). For example, you could use the match functions to check if the account number column on the data row follows a valid pattern.
