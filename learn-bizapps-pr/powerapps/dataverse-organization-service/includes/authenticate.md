To use the Dataverse ServiceClient, two primary approaches are available for handling authentication to a Dataverse environment. The first option is that ServiceClient can handle the authentication using its built-in capabilities to use the Microsoft Authentication Library (MSAL). Using this approach, ServiceClient internally manages the authentication process. The other option is entirely custom, where you provide a function that the ServiceClient calls to get an OAuth access token. Using this option, you're responsible for all aspects of the authentication process.

## Use ServiceClient built-in authentication

The approach you use to authenticate depends on the constructor you use on ServiceClient. Using a connection string you retrieve from your application configuration or Azure Key Vault is a typical choice. ServiceClient does have other constructor options that take parts of the connection string options as parameters if you prefer not to use a connection string. All of these options enable ServiceClient to use its built-in authentication capabilities. The following are some of the authentication scenarios that you can handle using this approach:

- OAuth using named account in Microsoft 365 with UX to prompt for authentication

- OAuth using current logged in user with fall-back UX to prompt for authentication

- Certificate based authentication

- ClientId and Client Secret based authentication

Here's an example of a connection string for ClientId and Client Secret based authentication:

```xml
<add name="MyDataverse"
  connectionString="
  AuthType=ClientSecret;
  url=https://contosotest.crm.dynamics.com;
  ClientId={AppId};
  ClientSecret={ClientSecret}"
  />
```

You can review the connection string [documentation](/power-apps/developer/data-platform/xrm-tooling/use-connection-strings-xrm-tooling-connect#connection-string-examples?azure-portal=true) for other option examples.

## Use ServiceClient with custom authentication

Using custom authentication allows you to control the token acquisition. When working with web applications or applications that are required to implement an on behalf of flow for user authentication, it's typically recommended to use this approach. When using this approach, you must provide a function that ServiceClient calls when it needs an access token for accessing Dataverse. The function takes a single parameter, an instanceUrl, and needs to return a string access token.

Here's an example of using custom authentication:

```
Uri instanceUrl = new Uri("https://YourEnvironmentName.crm.dynamics.com");

ServiceClient serviceClient = new ServiceClient(
    instanceUrl,
    MyTokenProvider,
    useUniqueInstance: true
);
```

In the above example, MyTokenProvider must have the necessary logic to acquire and return the token.

Here's an example of what that function would look like minus the logic to get the token:

```csharp
static async Task<string> MyTokenProvider(string instanceUrl)
{
    // Your logic to get the token

    return ">TheToken>";
}
```

## Check whether it's ready to use

Before using the instance of ServiceClient, you can check if it's ready for use by checking the **IsReady** property. If true, the Dataverse service is ready to accept requests. If false, you can evaluate the **LastError** and **LastException** properties for details on any problems that occurred.
