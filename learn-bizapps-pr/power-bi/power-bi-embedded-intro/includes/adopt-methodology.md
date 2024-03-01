The following steps outline the general methodology developers should follow to programmatically embed Power BI content into a new or existing app.

1. Prepare Power BI content for embedding.
1. Create a Microsoft Entra ID app registration.
1. Develop the app embedding code.
1. Enhance the user experience by using client API capabilities.

First, you need to have Power BI content ready to embed. Preparing content involves creating Power BI workspaces and publishing content to them. You can create and manage content in conventional ways by using Power BI Desktop and the Power BI service. The process of preparing Power BI content for embedding is described in the next unit.

Second, you need to create an *app registration* in Microsoft Entra. The app registration allows Microsoft Entra to know how to issue tokens, which will grant access to services and resources. Other Microsoft Entra setup might be required, depending on the embedding identity of your app.

> [!NOTE]
> To learn about embedding identities and app security setup, work through the [Set up permissions to embed Power BI content](/training/modules/power-bi-embedded-permissions-content/?azure-portal=true) module.

Next, you'll develop or extend your app solution with embedding code. This process involves importing specific NuGet packages. The NuGet packages help with server-side requirements to authenticate with Microsoft Entra ID, generate tokens, and discover Power BI content. The actual embedding of Power BI content happens client-side. A client API operation embeds a specific Power BI content item inside a `div` element.

> [!NOTE]
> To learn about developing embedding logic, work through the [Embed Power BI content](/training/modules/power-bi-embedded-content/?azure-portal=true) module.

The client APIs do much more than embed Power BI content. They support many operations to help you seamlessly integrate and enhance content. Capabilities include:

- **Programmatic interaction** - For example, your app can apply new filters to an embedded report.
- **Subscribable events** - Chart elements, such as a column of a column chart visual, menu extensions, and buttons, can trigger events that your app can respond to. For example, when the app user selects a button inside a Power BI report, your app can open a dialog window to enter and write back data to the app database.
- **Dynamic report layouts** - For example, your app user can choose light or dark-themed reports.
- **Bookmark interaction** - Your app can apply existing report bookmarks or create (and persist) personal bookmarks.
- **Report visual creation** - Your app can allow users to create report visuals or personalize existing report visuals.

> [!NOTE]
> To learn about the Power BI client APIs, work through the [Integrate content with the Power BI client APIs](/training/modules/power-bi-embedded-integrate/?azure-portal=true) module.
