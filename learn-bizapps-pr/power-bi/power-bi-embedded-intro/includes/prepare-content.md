You can create and manage Power BI content in conventional ways by using Power BI Desktop and the Power BI service. You don't need to create content specifically for embedding. However, you can achieve optimal and more visually pleasing results when you prepare for embedding.

## Prepare workspaces

A Power BI workspace is a logical container in the Power BI service for storing related items, such as semantic models and reports. It also forms a security boundary.

When you're creating content for embedding in an app, it's good practice to store it separate from other content that isn't related to the app. You can store it in one or more workspaces. Consider using multiple workspaces when many items exist and especially when different teams are responsible for the content. For example, one workspace could store financial reports, while another could store manufacturing reports. When the app supports creating new reports, consider creating a workspace for those reports as well.

The embedding identity that's used to embed workspace content must have specific permissions.

> [!NOTE]
> To learn about workspace permissions for internal and external users, work through the [Set up permissions to embed Power BI content](/training/modules/power-bi-embedded-permissions-content/?azure-portal=true) module.

When designing a multitenancy solution, you can achieve the separation of tenants by creating one workspace for each tenant. This design pattern is known as *workspace separation*.

> [!NOTE]
> To learn about workspace separation, work through the [Automate Power BI solution management](/training/modules/power-bi-embedded-automate/?azure-portal=true) module.

Each Power BI workspace is uniquely identified by its **GroupID**. Often, the app config file includes hard-coded references to the workspace GroupIDs. The Power BI REST API has operations to enumerate workspace items to retrieve specific properties for embedding purposes.

## Prepare semantc models

A Power BI semantic model is an item that represents a source of data. It typically represents a data model that includes tables, columns, hierarchies, relationships, and measures. Power BI reports and other items connect to semantic models.

When the app must restrict data access for specific users, semantic models can implement [row-level security (RLS)](/power-bi/admin/service-admin-rls/?azure-portal=true). For example, in embedded reports, the sales-representative app users are only allowed top view their assigned customers. However, the sales-manager app users, who view those same reports, can view all customers.

> [!NOTE]
> To learn how to restrict data access with RLS, work through the [Enforce data permissions for Power BI embedded analytics](/training/modules/power-bi-embedded-permissions-analytics/?azure-portal=true) module.

If the app embeds the Q&A experience, it's a good idea to optimize the dataset for Q&A. This process could involve:

- Setting column categorizations or sort orders.
- Defining synonyms or common phrases.
- Adding featured questions.

For more information, see [Best practices to optimize Q&A in Power BI](/power-bi/natural-language/q-and-a-best-practices/?azure-portal=true).

Each Power BI semantic model is uniquely identified by its **DatasetID**. The DatasetID is required when you're enforcing data access permissions or when embedding Q&A. The Power BI REST API has operations to look up DatasetID values.

## Prepare Power BI reports

A Power BI report page size is fixed. Therefore, at report-creation time, make sure that you set the page size to dimensions appropriate for your app. The app embeds content in `div` elements, so ensure that the report-page aspect ratio (width-to-height ratio) is in alignment with the `div` element size. When it aligns, no empty spaces will surround the embedded report.

To achieve a visually appealing result, strive to format reports to complement or enhance the embedding app. Consider formatting background colors, font properties, and other properties.

> [!TIP]
> To learn about the process for designing and delivering compelling Power BI reports, see the [Design effective reports in Power BI](/training/paths/power-bi-effective/?azure-portal=true) learning path.

Consider adding report elements that can enhance the app experience:

- The app can programmatically set slicers and filters.
- Buttons, when selected, can trigger client-side code that interacts with the app.
- The app can apply bookmarks, which capture specific report states.

If the Power BI report has a mobile view set up, you can embed the report in that view.

Each Power BI report is uniquely identified by its **ReportID**. The ReportID is required when you're embedding the report. The Power BI REST API has operations to look up ReportID values.

## Prepare Power BI visuals

When you're embedding a single visual sourced from a Power BI report, ensure that the visual dimensions are in alignment with the `div` element size. When it aligns, no empty spaces will surround the embedded visual.

Each Power BI report visual is uniquely identified by the ReportID and the visual name. The ReportID and visual name are required when you're embedding the visual. The Power BI REST API has operations to look up ReportID values. Use the client APIs to look up the visual name.

## Prepare paginated reports

Follow the preparation guidance provided for Power BI reports. Specifically, follow guidance relating to page size and designing visually appealing results.

Each paginated report is uniquely identified by its ReportID. The ReportID is required to embed a paginated report. The Power BI REST API has operations to look up ReportID values.

## Prepare dashboards

Power BI dashboards include tiles that are laid out across a single pane of glass. Pages and dashboard size properties aren't available. When embedding dashboards, you can scale the dashboard to fit the `div` element (known as *fit to width*) or you can render the dashboard as a vertical series of tiles (known as *one column*).

If the dashboard has a mobile view set up, you can embed the dashboard in that view.

Each dashboard is uniquely identified by its **DashboardID**. The DashboardID is required when you're embedding the dashboard. The Power BI REST API has operations to look up DashboardID values.

## Prepare for Q&A

As described in the datasets article, preparing Q&A for embedding involves optimizing the dataset for Q&A.

Consider applying a prepopulated question. That way, Q&A reveals the visual response to the question. Your app might be able to automatically generate the question based on the user's app interactions. As a result, Q&A can provide a way to present dynamically driven analytics.

> [!TIP]
> You can embed a Q&A visual from a Power BI report. This approach provides the ability to format the visual. Also, as a report visual, the app can apply filters to the visual.

Embedding the Q&A experience is based on a single semantic model.
