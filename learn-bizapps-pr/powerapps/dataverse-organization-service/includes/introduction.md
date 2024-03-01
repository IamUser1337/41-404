Microsoft Dataverse provides two primary APIs to work with data, using the **Dataverse SDK for .NET** and the **Web API**. The Web API can be used from any technology that can do HTTP requests. The Dataverse SDK for .NET targets applications built with .NET Framework or .NET Core.

This module focuses on the SDK for .NET and the organization service. For more information on the Web API, see [Use the Microsoft Dataverse Web API](/power-apps/developer/data-platform/webapi/overview/?azure-portal=true) in the Dataverse Developer Guide.

The DataverseSDK for .NET provides classes and tooling to make it easier for .NET developers to build Dataverse extensions and custom application logic that integrates with Dataverse. You can use the SDK for .NET when writing plug-ins, building custom web or client apps, Azure Functions and more.

The Dataverse SDK for .NET is referenced in your code using one of the two NuGet packages. For development of Dataverse plug-ins the [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.CoreAssemblies/?azure-portal=true) NuGet package would be used. For other .NET Framework or .NET Core code, the [Microsoft.PowerPlatform.Dataverse.Client](https://www.nuget.org/packages/Microsoft.PowerPlatform.Dataverse.Client/?azure-portal=true) NuGet package is recommended. This module covers the latter, however, many of the concepts apply to both.

## Dataverse Organization Service

Applications using the Dataverse SDK for .NET work with data and services in a Dataverse environment using an interface [IOrganizationService](/dotnet/api/microsoft.xrm.sdk.iorganizationservice?azure-portal=true) commonly called the Organization service. This interface defines the following primary methods for you to use:

- Associate - Creates a link between table rows.
- Create - Create new rows.
- Delete - Delete a row.
- Disassociate -Delete a link between table rows.
- Execute - Executes a message using a request/response pattern. This includes calling Dataverse Custom APIs.
- Retrieve - Retrieve a single row.
- RetrieveMultiple - Retrieve a collection of rows.
- Update - Updates an existing row.

The interface also provides async options for each using the **CreateAsync** pattern of method names.

Applications can get an instance of an object that implements **IOrganizationService** interface using the [ServiceClient](/dotnet/api/microsoft.powerplatform.dataverse.client.serviceclient?azure-portal=true) class. The **ServiceClient** handles the logistics of authentication and managing the connection to the Dataverse environment.

The following example gets an instance of ServiceClient and creates a new account table row.

```csharp
    ServiceClient serviceClient = new ServiceClient("<connectionString>");

    Entity newAccount = new Entity("account");
    newAccount["name"] = "Fourth Coffee";
    Guid accountid = serviceClient.Create(newAccount);
```

Each of the methods like Create are just helper methods for composing a request message, calling the Execute method, and  receiving a response message. To perform a Create operation, you would make the request using the CreateRequest class and receive a response message of CreateResponse. This pattern is the same for all Dataverse organization service operations including when you define Dataverse custom APIs.

## Use the Entity class

When you use the Organization service to work with data, you use the [Entity](/dotnet/api/microsoft.xrm.sdk.entity/?azure-portal=true) class to represent the data. The Entity class represents an instance of a Dataverse table row. When you work with the data, there are two programming styles you can use: late-bound and early-bound. The primary difference comes down to type conversion and type checking. Early bound provides compile-time checking of all types so that no implicit casts happen, while late-binding checks types when an action is performed. The Entity class requires types to be explicitly specified to prevent implicit casts.

### Late-bound

When you use the late-bound style, you use the Entity class directly without need to generate classes for your specific data model. Accessing columns of a data row (Entity) is done using the column's logical name. This can provide flexibility for code that might not know all the columns upfront. However, it doesn't benefit from the type checking and Intellisense help that the early-bound style has.

The following code is an example of using late-bound style:

```csharp
    Entity newAccount = new Entity("account");
    newAccount["name"] = "Fourth Coffee";
    newAccount["revenue"] = new Money(new decimal(5000000.00)); //Currency column
    newAccount["accountcategorycode"] = new OptionSetValue(1);  //Preferred customer choice column
```

### Early-bound

When you use the early-bound style, you work directly with a generated class specific to the Dataverse table you're accessing. The generated class inherits from the Entity class and has generated properties for each column on the Dataverse table. This approach can help improve productivity because type checking happens at compile time and you can take advantage of Visual Studio IntelliSense.

The following code is an example of using early-bound style:

```csharp
    var newAccount = new Account());
    newAccount.Name = "Fourth Coffee";
    newAccount.Revenue = new Money(new decimal(5000000.00)); //Currency column
    newAccount.AccountCategoryCode"] = new OptionSetValue(1);  //Preferred customer choice column
```

There are multiple options on how to generate the classes, the latest option is using the Power Platform CLI. The following code shows using the CLI modelbuilder command to generate classes for the account and contact tables.

```powershell
pac modelbuilder build --outdirectory Models --serviceContextName ContosoServiceContext --namespace Contoso --entitynamesfilter "account;contact"
```

Since all generated classes inherit from Entity, you can choose to mix the two styles in your code.
