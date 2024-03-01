Command bar buttons always show by default on the command bar. In some cases, the action of the button isn't viable to run. You can control the visibility using Power Fx logic. You can use Power Fx to do conditional checks against the runtime environment information and the selected data. For example, you could hide the button when a user creates a new row or if a data row has a specific value. You can also check the user's permissions to ensure that you aren't offering them an action they can't perform.

There are two options for checking permissions for the user of the app. You can use the DataSourceInfo function to broadly check permissions on the table at the data source level. This approach is good if you intend to create a new row in your action and ensure the user can complete the action. The DataSourceInfo doesn't have a data row context, so it can't determine if you can update a specific row. For example, you might be able to create a new row owned by your user but not be able to update a row owned by another user. To check permissions on a specific user, you can use the RecordInfo function. This function requires a reference to a data row and checks the user's permission in that context.

The following video will demonstrate how to use DataSourceInfo to improve the user experience of a command bar action.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5dXXO]

> [!NOTE]
> You can increase the video resolution by selecting the three dots, **Quality**, and selecting a higher bitrate. 

In addition to being helpful in checking permissions, the DataSourceInfo function also provides other valuable information about the data source columns. This information can be useful when composing command bar Power Fx expressions, so they don't contain values that are subject to change. For example, take the following **Notify** function that specifies the column name as a literal.

`Notify("Invalid value for Name")`

Dataverse allows changing the display name of table columns, in this example if the name was changed to "Product Name" the message would still be displayed as "Name". Using the following formula that calls the DataSourceInfo function the proper column name would be displayed without having to change the expression.

`Notify("Invalid value for " & DataSourceInfo(Products,DataSourceInfo.DisplayName,"sample_name")`

The [DataSourceInfo](/power-platform/power-fx/reference/function-datasourceinfo/?azure-portal=true) function can provide other useful values like min/max values, if the column is required and the max length allowed.

Using DataSourceInfo and RecordInfo can help improve the user experience of users interacting with your command bar customizations.
