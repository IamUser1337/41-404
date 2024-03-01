Various low-code tools and configuration-only features are available for building Microsoft Power Pages websites. Examples of these tools and features include lists, forms, multistep forms, and the ability to integrate other technologies such as SharePoint and Microsoft Power BI. However, you might encounter features that aren't easily set up by using the available low-code or no-code features.

The Liquid template language in webpages and templates extends your website and allows you to manipulate and display content in various ways.

You can also further extend Power Pages websites by using standard web technologies such as HTML, JavaScript, and Cascading Style Sheets (CSS).

Power Pages now supports controls that you can create by using the Power Apps component framework. These code components can provide an enhanced experience for users who are working with data on forms, views, and dashboards.

You might also encounter situations where you need to update or create data in Microsoft Dataverse without submitting a form. You can use the portals Web API to perform, create, read, update, and delete operations across all Microsoft Dataverse tables from your website pages. For example, you can create a new account, update a contact, or place a case on hold without sending the page to the server.

Common methods for communicating with external apps, such as payment gateways, include: 

- Build a custom API that you can call from the Power Pages website front end. 
- Create a standalone web application that you can embed into the Power Pages website and that can use Power Pages authentication for a seamless user experience.

After you've set up and customized your website, another concern that you might have is ensuring that your work is saved in a source control system and that you can deploy your website to a test or production environment as part of application lifecycle management (ALM).

## Server-side extensibility

Power Pages doesn't support client-side business rules or JavaScript web resources that are common with model-driven forms. As a result, website deployments might occasionally become blocked because expectations of the same, or similar, form behavior can't be met. Instead, lists, forms, and multistep forms include a custom JavaScript option that allows developers to add scripts that implement equivalent functionality in Power Pages.

However, Power Pages is based on model-driven apps that are underpinned by Dataverse. In fact, Power Pages delivers functionality that's already available in a model-driven app, but only to website users. As a result, you should consider the following factors:

- Table-scope business rules still apply because they're implemented on the server side.

- Classic workflows and Microsoft Power Automate flows are still triggered, regardless of whether a triggering action was run inside a model-driven app or a website. You can also call the classic workflows explicitly by using form configuration on the website.

- When a website user interacts with Dataverse records, the server-side code runs as usual. Developers can pass relevant context to plug-ins when the records have been updated by website users. This approach adds some server-side code extensibility to Power Pages and enables other integration scenarios.
