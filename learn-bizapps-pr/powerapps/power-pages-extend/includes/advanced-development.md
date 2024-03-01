Using JavaScript and CSS to manipulate client-side visibility and functionality of webpages can help you achieve considerable success in satisfying some key business requirements. To implement more complex scenarios, a developer can be creative and use other strategies to extend Power Pages websites.

## Partner libraries

JavaScript can use other JavaScript libraries that deliver functionality, such as UX enhancements (masked controls), real-time communications (SignalR), sophisticated UI frameworks (Angular, Vue, React), and other various business services like address validations, map API, routing services, logistics, and so on.

Power Pages websites create a clean, responsive layout with predictable element names, which helps make manipulating the data and UI easier.

For an example of a sophisticated implementation that Power Pages websites host and that uses Angular framework for communications, see [Set up an event website (Dynamics 365 Customer Insights - Journeys)](/dynamics365/marketing/set-up-event-portal/?azure-portal=true).

## Code components

Professional developers can use Power Apps component framework to create code components for model-driven and canvas apps. These code components can provide an enhanced experience for users who are working with data on forms, views, and dashboards. 

Power Pages websites now support controls for model-driven apps that you've created by using Power Apps component framework. To use code components in webpages, follow these steps:

1. Create and package your code component or use an existing code component.

1. Add the code component to a column on a model-driven form.

1. Set up the form for the code component.

For more information, see [Use code components in Power Pages](/power-pages/configure/component-framework?azure-portal=true).

Professional developers can use portals Web API to interact with Dataverse data directly from JavaScript, which creates a richer user experience within webpages. The Power Pages portals Web API enables implementation of create, read, update, and delete operations across all Microsoft Dataverse tables.

You can help protect the data by using a combination of web roles and table and column permissions to ensure that website visitors only have the appropriate access to Dataverse rows and columns.

For more information, see [Overview of the Power Pages portals Web API](/power-pages/configure/web-api-overview?azure-portal=true).

## Companion apps and services

Situations could arise in which you need to communicate securely with external services while maintaining the security context, such as when you're processing online payments. Power Pages enables this scenario by providing support for [OAuth 2.0 implicit grant flow within your Power Pages site](/power-pages/security/oauth-implicit-grant-flow?azure-portal=true).

This feature allows a customer to make client-side calls to external APIs and help secure them by using OAuth implicit grant flow. This method helps ensure that the identity information of a signed-in user is passed in a more secure manner to the external calls.

In this scenario, you'll build a custom web application, and then Power Pages websites would communicate to this application by using JavaScript to call the API.  

CSS and JavaScript enable many integration and extensibility scenarios that range from simple UI adjustments to validation and data input to sophisticated client-side applications that interact with other services.	
