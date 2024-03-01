> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE50TBD]

You can create lists on SharePoint, and you can use these lists as data points to track the data that the organization needs in case your design only includes canvas apps. Model-driven apps rely on Microsoft Dataverse for data storage.

Occasionally, apps access data and tables that are already being used from another system that the organization has been using for some time.

In [Microsoft Power Apps](https://make.powerapps.com/?azure-portal=true), you can create a connection to one or more data sources, delete a connection, or update the app's credentials.

Your canvas app's data connection can connect to SharePoint, Microsoft SQL Server, Microsoft Office 365, OneDrive for Business, Salesforce, Microsoft Excel, and many other [data sources](/power-apps/maker/canvas-apps/connections-list/?azure-portal=true).

Other types of data sources are available that aren't tables, such as email, calendars, Twitter, and notifications.

By using the [Gallery](/power-apps/maker/canvas-apps/controls/control-gallery/?azure-portal=true), [Display form](/power-apps/maker/canvas-apps/controls/control-form-detail/?azure-portal=true), and [Edit form](/power-apps/maker/canvas-apps/controls/control-form-detail/?azure-portal=true) controls, you can create an app that reads and writes data from a data source.

Power Apps includes a powerful set of functions for filtering, sorting, and shaping tables of data in a canvas app: [Filter](/power-apps/maker/canvas-apps/functions/function-filter-lookup/?azure-portal=true), [Sort](/power-apps/maker/canvas-apps/functions/function-sort/?azure-portal=true), and [AddColumns](/power-apps/maker/canvas-apps/functions/function-table-shaping/?azure-portal=true) functions, to name a few. With these functions, you can provide your users with focused access to the information that they need. For people who have a database background, using these functions is the equivalent of writing a database query.

An important key to building efficient apps is to minimize the amount of data that must be brought to your device. For example, you might need only a few records from a million, or a single aggregate value can represent thousands of records. Alternatively, you might need only the first set of records to be retrieved and the rest brought in when the user indicates that they want more. By being focused, you can dramatically reduce the processing power, memory, and network bandwidth that your app needs. As a result, you observe quicker response times for your users, even on mobile phones that are connected through a cellular network.

*Delegation* is where the expressiveness of Power Apps formulas meets the need to minimize data that moves over the network. Essentially, Power Apps delegates the processing of data to the data source rather than moving the data to the app for processing locally.

Working with large datasets requires you to use data sources and formulas that can be delegated.

If the data source that you need to access with your app isn't in the cloud, you can install an on-premises data gateway to transfer data quickly and more securely between your app and your internal data source. You can connect to on-premises data over the [connectors](/connectors/connector-reference/connector-reference-powerapps-connectors/?azure-portal=true) that use the data gateway.

## Recommended content

For more information, see the following articles:

- [Manage connections in canvas apps](/power-apps/maker/canvas-apps/add-manage-connections/?azure-portal=true)

- [Understand delegation in a canvas app](/power-apps/maker/canvas-apps/delegation-overview/?azure-portal=true)

- [Manage an on-premises data gateway in Power Apps](/power-apps/maker/canvas-apps/gateway-management/?azure-portal=true)
