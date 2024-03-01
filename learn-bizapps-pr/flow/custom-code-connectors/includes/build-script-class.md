In this unit, you'll explore how to build your C# script class to implement your transformation logic.

Custom code that's used with a connector must meet the following requirements:

-   The class name must be **Script**.

-   The Script class must implement **ScriptBase**.

-   The Script class must implement a method named **ExecuteAsync**.

-   Custom code must take fewer than five seconds to run.

-   Custom code must be less than 1 MB in total.

-   Only one Script file or class is supported.

## Explore ScriptBase

**ScriptBase** is a class that the custom connector infrastructure provides with supporting helper methods and interfaces. Your **Script** class needs to use this abstract class as its base class.

```json
public class Script : ScriptBase
{
    public override Task<HttpResponseMessage> ExecuteAsync()
    {
        // Your code here
    }
}
```

In addition to the **ExecuteAsync** method, this class also has the **CreateJsonContent** helper method that you use to create a **StringContent** object from the serialized JSON. For example, in the following code, the **CreateJsonContent** helper method populates **response.Content** from the transformed response that was built.

```json
// Wrap the original JSON object into a new JSON object with just one key ('wrapped')
var newResult = new JObject
{
    ["wrapped"] = result,
};
      
    response.Content = CreateJsonContent(newResult.ToString());
```

The **ScriptBase** class also provides a **CancellationToken** property. If you make calls by using **SendAsync**, you'll use the **CancellationToken** property. If the request takes too long or a cancellation is requested, the method signals the **CancellationToken** that's passed to it.

The **ScriptBase** class also has a **Context** public property, which is available to your logic to provide context for the request that's being processed. The **Context** property is of the type **IScriptContext** and has the following useful properties and methods:

-   **OperationId** - This property is most useful when you need to identify which operation is being processed so that your logic can provide the correct transformations.

-   **Request** - This method is the **HttpRequestMessage** for the operation that's being processed. If you need to transform the request, you modify this method, and then pass it to **SendAsync** to send the request to the service.

-   **Logger** - This method provides you with an instance of an **ILogger** that you can use to log diagnostic information from your code to the Code Logs for the connector operation.

-   **SendAsync** - Use this property to send an HTTP request to the service. You should use this method instead of making your own HttpClient.SendAsync call.

## Compile your code locally

Compiling your code locally can help make it easier for you to identify compilation problems. To compile your code locally, you'll need to create a project on your local computer, and then create files for the **ScriptBase** class and the **IScriptContext** interface. You'll copy the code for these files from the [Definition of supporting classes and interfaces](/connectors/custom-connectors/write-code?azure-portal=true#definition-of-supporting-classes-and-interfaces) documentation.

The [Microsoft/MTC_CustomConnectorCodeProject](https://github.com/microsoft/MTC_CustomConnectorCodeProject/?azure-portal=true) open-source project on GitHub can also be helpful for local development. This project provides a console project presetup for custom code development.

## Supported namespaces

The custom code that you implement is limited to a set of supported namespaces. These namespaces are mostly a collection of common System.\* namespaces, including logging and Newtonsoft JSON, to help support the logic in your custom code. For a complete list of the currently supported namespaces, go to [Supported namespaces](/connectors/custom-connectors/write-code?azure-portal=true#supported-namespaces).

Additionally, your custom code might not reference any other .NET assemblies, so it's limited to the logic that you put in your uploaded script.

## Other custom code examples

To learn more about different types of transformations that you'll complete by using custom code, you can browse examples of published Microsoft Power Platform connectors. By [searching for ScriptBase](https://github.com/microsoft/PowerPlatformConnectors/search?q=ScriptBase/?azure-portal=true) on the **PowerPlatformConnectors** public repository, you can view the current connectors that implement custom code.

