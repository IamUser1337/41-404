
Microsoft Power Platform is made powerful by its ability to use data across many platforms. To work across multiple data platforms, components of Microsoft Power Platform use connectors. You can think of connectors as a bridge from your data source to your app or workflow. This bridge allows information to be conveyed back and forth. Connectors allow you to extend your business solutions across platforms and add functionality for your users.

## Data Sources

To understand the types of connectors and their capabilities, you must first understand the types of data sources to which they connect. The two types of data sources are tabular, and function based.

**Tabular data** - A tabular data source is one that returns data in a structured table format. Power Apps can directly read and display these tables through galleries, forms, and other controls. Additionally, if the data source supports it, Power Apps can create, edit, and delete data from these data sources. Examples include Microsoft Dataverse, SharePoint, and SQL Server.

**Function-based data** - A function-based data source is one that uses functions to interact with the data source. These functions can be used to return a table of data but offer more extensive action such as the ability to send an email, update permissions, or create a calendar event. Examples include Office 365 Users, Project Online, and Azure Blob Storage.

Both data source types are commonly used to bring data and incremental functionality to your solutions. As you can see, connecting to data sources allows you to integrate disparate parts of your business solutions to build them out cohesively. Now that you understand more about data sources, you're ready to learn about connectors.

Connectors are the bridges from your data source to your app, workflow, or dashboard. Microsoft Power Platform has more than 1,000 connectors available to common data sources. Connectors are divided into standard and premium. Some popular standard connectors are SharePoint, Outlook, and YouTube. Premium connectors require added licensing for your app and/or users. A few premium connectors are SQL Server, Survey Monkey, and Mail Chimp. The connector reference in the summary and resources unit lists all connectors and whether they're considered standard or premium. You can also use AppSource to source and install apps and use the connectors to non-Microsoft services.

Connectors can provide input and output between the data source and Power Platform, which can accelerate the delivery of Microsoft Power Platform business solutions. For instance, using Dynamics 365 apps such as Customer Service, you can set up Power Automate to notify users when specific customer types are added. Or you can use a SharePoint document library to store files that are fed into Power Apps to manage and distribute. Microsoft also provides connectors to their Azure services, providing advanced AI techniques to do tasks such as reading text off images or cognitive services like recognizing faces in images.

All Microsoft Power Platform business solutions can be used and implemented into Microsoft 365 apps such as Teams. This integration allows users to play Power Apps within Teams or run Power Automate from actions and events within Teams.

## Triggers and Actions

Once you established a data source and configured your connector, there are two types of operations you can use, triggers or actions.

**Triggers** are only used in Power Automate and prompt a flow to begin. Triggers can be time based, such as a Power Automate flow that begins every day at 8:00 am. They could be based off an action like creating a new row in a table or receiving an email. You always need a trigger to tell your workflow when to run.

**Actions** are used in Power Automate and Power Apps. Actions are prompted by the user or a trigger and allow interaction with your data source by some function. For example, an action would be sending an email in your workflow or app writing a new line to a data source.

Now that you understand what connectors are and how to use them, examine the different connectors available. 

## Types of connectors

### Standard Connectors

Standard tier connectors are connectors that are included in your standard Microsoft 365 subscription. Standard connectors cover many of the most used data sources such as SharePoint, OneDrive, and Power BI and third-party data sources such as Google Drive, Twitter, GitHub, and more.

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-08.png" alt-text="Screenshot of available standard connectors.":::

### Premium Connectors

While standard connectors are available with a standard Microsoft 365 subscription, premium connectors are only available when you have the appropriate standalone plans. These plans include a Power Apps per user plan, or a Power Automate per user plan. The main advantage of premium connectors is that they allow you to connect to a larger number of services. Most premium connectors cover external applications such as Salesforce, DocuSign, Survey Monkey, Amazon, and so on. There are several Microsoft applications that use premium connectors such as Dynamics 365. The premium stamp identifies premium connectors.

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-09.png" alt-text="Screenshot of available premium connectors.":::

### Custom Connectors

If any of the over 1,000 connectors don't provide you with what you need, you can build a custom connector. Custom connectors allow you to extend your app by calling a publicly available API, or a custom API you're hosting in a cloud provider, such as Azure. API stands for Application Programming Interface and holds a series of functions available for developers. Connectors work by sending information back and forth across these APIs and gathering available functions into Power Apps or Power Automate. Because these connectors are function-based, they call specific functions in the underlying service of the API to return the corresponding data.

An advantage of building custom connectors is that they can be used in different platforms, such as Power Apps, Power Automate, and Azure Logic Apps.

You can create custom connectors using three different approaches:

- [Using a blank custom connector](/connectors/custom-connectors/define-blank)

- [Using an OpenAPI definition](/connectors/custom-connectors/define-openapi-definition)

- [Using a Postman collection](/connectors/custom-connectors/define-postman-collection)

While the requirements for each approach vary, they all require a Power Apps per app or per user plan. Each link above points to the instructions for each approach.

> [!Note] 
> The purpose of this module is to help you better understand data sources and connectors as a whole, but if you would like to learn more about custom connectors and even walk through an exercise to build one, check out the module [**Use custom connectors in a Power Apps canvas app**](/training/modules/use-custom-connectors-in-powerapps-canvas-app/).