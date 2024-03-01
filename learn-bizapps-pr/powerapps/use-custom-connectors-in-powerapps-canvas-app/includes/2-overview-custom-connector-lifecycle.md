Before you start creating custom connectors, you need to know all the details for each of the steps involved in the custom connector lifecycle. The following diagram shows all the tasks involved in creating and using custom connectors.

> ![Diagram of the Authoring Steps for creating and using custom connectors.](../media/authoring-steps.png)

Build and secure your API
-------------------------

A custom connector is a wrapper around a REST API that lets an underlying service communicate with Power Apps, Power Automate, or Azure Logic Apps. Make sure that you have a fully functioning API before you start creating custom connectors.

You can use any language and platform for your API, as long as it's made
available as a REST API or SOAP API. Here are a few examples:

- Publicly available APIs like
  [NOAA](https://www.ncdc.noaa.gov/cdo-web/webservices/v2/?azure-portal=true), [US Census
  API](https://www.census.gov/developers/?azure-portal=true), or [EU Open Data
  Portal](https://data.europa.eu/euodp/en/developerscorner/?azure-portal=true).

- An API that you create and deploy to any cloud hosting provider,
  such as Azure, Heroku, or Google Cloud.

A custom line-of-business API that's deployed to your network. You can
connect to the API if it's available over the public internet, or you
can connect to it through a gateway (currently available in Power Automate and Power Apps)

For Microsoft technologies, we recommend one of these platforms:

- [Azure Functions](https://azure.microsoft.com/services/functions/?azure-portal=true)

- [Azure Web
  Apps](https://azure.microsoft.com/services/app-service/web/?azure-portal=true)

- [Azure API
  Apps](https://azure.microsoft.com/services/app-service/api/?azure-portal=true)

To secure your API and connectors, you can use one of these standard
authentication methods ([Azure Active
Directory](https://azure.microsoft.com/develop/identity/?azure-portal=true) is
recommended):

- [Generic OAuth 2.0](https://oauth.net/2/?azure-portal=true)

- OAuth 2.0 for specific services, such as Microsoft Entra ID,
  Dropbox, GitHub, and Salesforce

- [Basic
  Authentication](https://swagger.io/docs/specification/authentication/basic-authentication/?azure-portal=true)

- [API
  Key](https://swagger.io/docs/specification/authentication/api-keys/?azure-portal=true)

You can set up Microsoft Entra ID authentication for your API in the Azure portal
so you don't have to implement authentication through code. If needed,
you can require and enforce authentication through your API's code. For
more information about Microsoft Entra ID for custom connectors, see
[Secure your API and connector with Azure
AD](/connectors/custom-connectors/azure-active-directory-authentication/?azure-portal=true).

Describe the API and define the custom connector
------------------------------------------------

After you have an API, the next step to consider is how to describe the API's interface and its operations so that Power Apps, Power Automate, and Azure Logic Apps can communicate with the API. After you determine how to describe the API, you can create the connector, which then registers it with the appropriate services.

Use one of the following approaches to describe your API:

- An OpenAPI definition (formerly known as a Swagger file). For more information, see
  [Create a custom connector from an
  OpenAPI](/connectors/custom-connectors/define-openapi-definition/?azure-portal=true)
 and [What is Swagger](http://swagger.io/getting-started/?azure-portal=true).

- A Postman collection. For more information, see [Create a Postman collection for a custom
  connector](/connectors/custom-connectors/create-postman-collection/?azure-portal=true),
  [Create a custom connector from a Postman
  collection](/connectors/custom-connectors/define-postman-collection/?azure-portal=true),
  and [Postman documentation](https://www.getpostman.com/docs/?azure-portal=true).

- You can also start with a blank custom connection using the custom connector wizard in
  Power Apps and Power Automate. For more information, see [Create a custom connector from
  scratch](/connectors/custom-connectors/define-blank/?azure-portal=true)
  for additional information.

OpenAPI definitions and Postman collections use a different format, but
both are language-independent, machine-readable documents that describe
your API's operations and parameters. You can generate these documents
from various tools, based on the language and platform used by your API.
Behind the scenes, Power Apps, Power Automate, and Azure Logic Apps use
OpenAPI to define connectors.

Use the custom connector
------------------------

You can use your custom connector the same way that you use any built-in
connectors. You create the connection to the API and call any operations
provided by the API the same way that you call operations for built-in
connectors.

Connectors created in Power Apps or Power Automate can be used in both
services, but connectors created in Azure Logic Apps cannot be used
directly in other services. However, a connector can be easily recreated
using the same OpenAPI definition or Postman collection used to create
the Azure Logic Apps connector.

For more information about using custom connectors from Power Apps, Power Automate, and Azure Logic Apps:

- [Use a custom connector from a Power Apps
  app](/connectors/custom-connectors/use-custom-connector-powerapps/?azure-portal=true)

- [Use a custom connector from a
  flow](/connectors/custom-connectors/use-custom-connector-flow/?azure-portal=true)

- [Use a custom connector from a logic
  app](/connectors/custom-connectors/use-custom-connector-logic-apps/?azure-portal=true)

Share the custom connector
--------------------------

Connectors can be shared with other users in your organization the same
way you share resources in Power Apps, Power Automate, and Azure Logic
Apps. For more information, see [Share a custom connector in your
organization](/connectors/custom-connectors/share/?azure-portal=true).

Certify the custom connector
----------------------------

If you want to share the connector with all users in Power Apps,
Power Automate, and Azure Logic Apps, you can submit the connector for
Microsoft certification. During this process, Microsoft reviews the
connector, checks for technical and content compliance, and validates
functionality for Power Apps, Power Automate, and Azure Logic Apps. For more information, see [Submit your connector for Microsoft certification](/connectors/custom-connectors/submit-certification/?azure-portal=true).
