Data is at the core of apps, including those apps you build in Power Apps. Data is stored in a data source, and you bring that data into your app by creating a connection. The connection uses a specific connector to talk to the data source. Power Apps has connectors for many popular services and on-premises data sources, including SharePoint, SQL Server, Office 365, Salesforce, and Twitter.

A connector is a wrapper around an API that allows the underlying service to communicate with Power Automate and Power Apps. If one of the provided connectors doesn’t work with your data source, a developer can create an API if one doesn’t already exist. Once the API has been created, a custom connector can be created to describe the API and a maker can then use the connector without needing to write code. Often the API exists and it’s just a matter of describing it with a custom connector definition.

Once an API is available, setting up a custom connector using the wizard does not always require a developer, but it is an advanced task that has low-code requirements. When defining the custom connector, you will provide several definitions to include the actions, triggers, and references. Detailed steps to create a custom connector can be found [here](/connectors/custom-connectors/define-blank).

It's important to look at the connector details when you're looking at using it for integration to ensure that you've met the licensing requirements to fall within the throttling for your particular scenario.

Model-driven apps have their own data source, Dataverse. But they can also integrate with other apps and services depending on the need. Canvas apps, Power Automate, Power BI, and Power Virtual Agents all need a data source and rely heavily on connectors.

:::image type="content" source="../media/connectors-0d0726c0.png" alt-text="Screenshot of a list of connectors.":::


There are hundreds of connectors available. For a full list of connectors, visit [this page](/connectors/connector-reference/connector-reference-powerapps-connectors).
