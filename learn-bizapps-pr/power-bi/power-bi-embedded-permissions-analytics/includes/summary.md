When all app users can view all data in Power BI embedded content, you don't need to take special steps. However, when app users should be able to view subsets of model data, it's critical that your solution enforces data permissions.

Typically, you'll enforce data permissions by setting up models to use RLS. However, when the source data is stored in an Azure SQL Database, and the dataset represents an internal-hosted DirectQuery model, you can use RLS that's set up in the source data. In this case, you need to use token-based identity.

Many good development practices are available for you to apply to ensure that data permissions are enforced accurately and efficiently.

> [!TIP]
> If you want to develop an app that embeds Power BI content, see [Power BI Developer in a Day course](https://aka.ms/deviad-online-course/?azure-portal=true). This course includes a self-study kit that guides you through the process of developing an ASP.NET Core MVC app. It explores working with static and dynamic rules.
