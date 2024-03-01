Microsoft Dataverse exposes events to indicate where the process is currently executing in the pipeline. We can handle these events to do things like validate data, prevent transactions from completing, or automate any business logic you can't accomplish by declarative means.

We can subscribe to these events by registering .NET assemblies (called plug-ins) to execute custom logic whenever the given event occurs. We perform the registration by using a tool called the Plugin Registration Tool. For more information on the Plug-in Registration tool, see the [Register a plug-in](/power-apps/developer/data-platform/register-plug-in?azure-portal=true) tutorial.

At a high level, handling events involves three things. First, you must subscribe to a specific message representing the type of operation (or event) currently occurring (or about to occur), such as Create, Retrieve, Update, etc. You must also indicate where in that event pipeline you would like your logic to execute (that is before or after the operation). You can also handle events before validation occurs, a convenient method that you can use to perform advanced validation logic that you can't accomplish via business rules or workflows. Lastly, you must indicate the execution mode you want the logic to run (synchronously or asynchronously).

Let's now go into these three areas in more detail.

## Event messages

Dataverse exposes many messages that are published when various data operations occur. For more information on these messages, see [Use messages with the Organization service](/power-apps/developer/data-platform/org-service/use-messages?azure-portal=true&tabs=sdk).

The basic data operations exposed by Dataverse are:

-   Create

-   Retrieve

-   RetrieveMultiple

-   Update

-   Delete

-   Associate

-   Disassociate

Also, there are various messages that are exposed contextually, depending on what type of table you're handling. For example if my table has a rollup column, I can implement an event handler on the CalculateRollupField event message.

Generally, we can find an inventory of these custom messages made available via Dataverse by searching through the
[Microsoft.Sdk.Messages](/dotnet/api/microsoft.xrm.sdk.messages/?azure-portal=true) namespace for any classes whose name ends in *\Request*. Another way to see which messages are available for a given type of table is to navigate table-message combinations via the Plugin Registration tool.

Also, we can create and expose our own messages by creating custom *Actions*. For more information on Actions, see [Create your own actions](/power-apps/developer/data-platform/custom-actions?azure-portal=true).

## Event pipeline

In addition to subscribing to specific messages or event types, Dataverse also exposes a way to specify where in the pipeline that event executes your custom logic. For ASP.NET developers, this is like how you work with page lifecycles within a web application. This approach is a common development pattern for publish-subscribe architectures and should feel familiar to developers with experience with other event frameworks.

### Pre-validation

The Pre-validation event occurs first in the pipeline, before any security checks are performed. It's intended for usage to ensure that the user executing the current transaction has the correct permissions needed to perform the intended operation.

As a developer, you can use this event to run validation logic and cancel the operation before the transaction occurs. For example, if configured to run whenever a table is updated, you can cancel the operation before the update occurs by throwing an *InvalidPluginExecutionException* method within your plugin's execution logic. For more information on execution context, see [Understand the Execution Context](/power-apps/developer/data-platform/understand-the-data-context?azure-portal=true).

### Pre-operation 

Use this event if you want to change any values of the table prior to it being saved.

### Post-operation

Use this event to modify any message properties before the requestor of the request gets the response. Make sure not to apply any updates to the corresponding table at this point, as it will trigger another update event!

## Execution modes (synchronous versus asynchronous)

You can configure plug-ins to run synchronously or asynchronously, depending on what type of pipeline operation is being handled.

### Synchronous

Plug-ins registered in this mode will run as soon as the processing of the event reaches their execution pipeline stage, and the entire operation won't proceed until the logic has completed execution. If multiple plug-ins are registered to run against the same pipeline stage, the execution order attribute (specified via the Plug-in Registration tool) will determine which one runs first.

### Asynchronous

Plug-ins registered in this mode dispatch as a system job to the asynchronous service, which executes their logic after the given operation completes. For more information on how system jobs work, see [Asynchronous service](/power-apps/developer/data-platform/asynchronous-service?azure-portal=true).

> [!NOTE]
> You can only register asynchronous plug-ins for the **PostOperation** stage of the Event Pipeline.
 
