When generating an embed token, you can set effective identity when working with the *For your customers* scenario.

Your app logic will first create a list of one or more `effectiveidentity` objects. Each object can include the following parameters.

- `Datasets`: (Required) A list of DatasetIDs.

- `Username`: (Optional) For internal-hosted models, it's a text value to be returned by the `USERNAME` or `USERPRINCIPALNAME` function. For external-hosted models, it's the username to connect to the model.

- `Roles`: (Optional) List of role names.

- `CustomData`: (Optional) A text value to be returned by the `CUSTOMDATA` function.

- `IdentityBlob`: (Optional) An Azure AD access token that's used for token-based identity with a DirectQuery connection to a Microsoft Azure SQL Database. It allows you to enforce data permissions without data model RLS. We'll describe this topic later in this unit.

You might pass in a list of datasets because the embed token will be used to embed many Power BI artifacts that connect to different datasets or because a dashboard is composed of tiles that connect to multiple datasets. When a list of multiple roles is passed in, all roles are simultaneously enforced, meaning that the user can view the union of the data that the roles grant.

The following example creates a list that contains one `effectiveidentity` object. It passes in the username of the current app user, the **Region** role, and the first (and perhaps only) dataset that's found in the workspace:

```csharp
// Create effective identity for the first dataset
var datasetId = datasets[0].Id.ToString();
var effectiveIdentities = new List<EffectiveIdentity>() {
	new EffectiveIdentity(
		username: userProfile.Username,
		roles: new List<string> {"Region"},
		datasets: new List<string> {datasetId})
};
```

Next, to generate an embed token, the app will pass the list to the `identities` parameter of the `GenerateTokenRequestV2` method. Other methods generate embed tokens, each allowing you to pass in a list of effective identities.

```csharp
// Bundle token requests for the reports, datasets, and the workspace
var tokenRequest = new GenerateTokenRequestV2(
    reports: reportTokenRequests,
    datasets: datasetTokenRequests,
    targetWorkspaces: workspaceRequests,
    identities: effectiveIdentities
) ;
```

The following topics provide further details about setting effective identity for each Power BI dataset type.

### Set effective identity for internal-hosted import tables

Consider the following parameters when you're passing effective identity to connect to an internal-hosted model with import tables:

- At least one role must be defined in the model.

- The username must be passed, but it doesn't need to be a real username. The value that's passed in is returned by the `USERNAME` or `USERPRINCIPALNAME` function.

- At least one role must be defined by the effective identity.

### Set effective identity for internal-hosted DirectQuery tables

To set effective identity for internal-hosted DirectQuery tables, you'll use the same guidance for internal-hosted import tables.

In addition, you can use *token-based identity*. Token-based identity allows you to specify the effective identity for an embed token by using an Azure AD access token, but only when the source is an Azure SQL Database. When you're generating the embed token, your app will pass the access token to the `IdentityBlob` parameter. In this case, you don't need to pass a value to the `username` parameter.

Using token-based identity requires the dataset owner to set up the data source to use the end users' OAuth2 credentials. This way, Power BI uses the effective identity username to connect to the data source. It means that the database can enforce RLS instead of the data model.

For more information about token-based identity, see [Security features in Power BI Embedded](/power-bi/developer/embedded/embedded-row-level-security).

### Set effective identity for Azure Analysis Services

To set effective identity when using an Azure Analysis Services model, you need to make sure that the embedding identity (service principal or master user account) has at least read permission on the model.

When no effective identity is passed, and the embedding identity account is an Analysis Services admin, all app users can view all model data. When the embedding identity account isn't an Analysis Services admin, data visibility is limited by that account's assigned roles.

> [!NOTE]
> When you're using service principal with an Azure Analysis Services model, the service principal must have Azure Analysis Services instance permissions. Using a security group that contains the service principal for this purpose doesn't work.

Consider the following parameters when you're passing effective identity to work with an Azure Analysis Services model:

- At least one role must be defined in the model.

- The username must be a master user account (UPN format) or service principal (ObjectID).

- When no roles form part of the effective identity, roles that are assigned to the effective identity account are applied.

- The `USERNAME` function will return the effective identity username.

### Set effective identity for SQL Server Analysis Services

To set effective identity when using a SQL Server Analysis Services model, you need to make sure that the gateway data source credentials are set as an Analysis Services admin.

The effective identity (service principal or master user account) must be a gateway admin or have **ReadOverrideEffectiveIdentity** permissions on the gateway data source. You can set this permission only by using the Power BI REST API.

When no effective identity is passed and the embedding identity account is an Analysis Services admin, all users can view all model data. When the embedding identity account isn't an Analysis Services admin, data visibility is limited by that account's assigned roles.

Consider the following parameters when you're passing effective identity to work with a SQL Server Analysis Services model:

- At least one role must be defined in the model.

- The username must be a Windows account, using UPN or DOMAIN\username format.

- The username must have read permission on the model.

- When no roles form part of the effective identity, roles that are assigned to the effective identity username are applied.

- The `USERNAME` function will return the effective identity username.

- Use of the `CUSTOMDATA` function isn't supported.

### Compare dataset types

The following table compares effective identity parameter settings for the four dataset types.

|     Parameter                 |     Internal-hosted import tables                                                             |     Internal-hosted DirectQuery   tables                                                       |     Azure Analysis  Services                                                                                                          |     SQL Server Analysis Services                                                                                          |
|-------------------------------|-----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
|     Username                  |     Any text value that will be returned by the `USERNAME` and `USERPRINCIPALNAME` functions    |     Any text value that will be returned by the `USERNAME` and `USERPRINCIPALNAME` functions     |     It's used to authenticate with the service. It must be a master user account (UPN format)   or service principal (ObjectID).    |     It's used to   authenticate with the service. It must be a Windows account, using UPN or DOMAIN\username   format.    |
|     CustomData                |     Supported                                                                                 |     Supported                                                                                  |     Supported                                                                                                                         |     Not supported                                                                                                         |
|     Roles                     |     At least one role must be defined by the effective identity                             |     At least one role must be defined by the effective identity                              |     When no role is passed, roles that are assigned to the effective identity account are applied                                            |     When no role is   passed, roles that are assigned to the effective identity account are applied                                |
|     IdentityBlob              |     No                                                                                        |     Yes, when source data is an Azure SQL Database (that should enforce RLS requirements)    |     No                                                                                                                                |     No                                                                                                                    |
|     Additional information    |                                                                                               |                                                                                                |                                                                                                                                       |     Requires a gateway. The effective identity account must be a gateway admin.                                  |
