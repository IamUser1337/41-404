Microsoft Power BI is a collection of software services, apps, and connectors that work together to turn your unrelated sources of data into coherent, visually immersive, and interactive insights. Whether your data is a simple Microsoft Excel workbook or a collection of cloud-based and on-premises hybrid data warehouses, Power BI helps you connect to your data sources, visualize (or discover) what's important, and share that with anyone you want.

![Diagram showing Dataverse reporting options.](../media/3-power-bi.png)

Power BI can be simple and fast, capable of creating quick insights from an Excel workbook or a local database. However, Power BI is also robust and enterprise-grade, ready for extensive modeling and real-time analytics and for custom development. Therefore, while it can be your personal report and visualization tool, it can also serve as the analytics and decision engine behind group projects, divisions, or entire corporations.

A key advantage of Power BI is the ability to include many data sources such as Salesforce, tables that are embedded in webpages, Microsoft Access, Excel, SQL databases, Mailchimp, and Dataverse.

Power BI is a self-service platform that helps users interact with prebuilt datasets and reports and to create their own visualizations.

The fundamental components of Power BI are:

- **Datasets** - A collection of data from one or more data sources that are cleansed, transformed, and modeled.
- **Visualizations** - A visual representation of data, such as a chart or a color-coded map. Power BI has many types of visualizations.
- **Reports** - A collection of visualizations on one or more pages.
- **Dashboards** - A collection of visuals on a single page that you can share with others. Dashboards can be embedded in Power Apps.
- **Tiles** - A single visualization on a dashboard. Tiles can be embedded in Power Apps.
- **Apps** - A collection of reports and dashboards that can be shared.

## Power BI capabilities

Power BI offers a range of out-of-the-box visualization options that are available directly from the **Visualizations** pane. When you select the fields that you want to display in a visualization, you can experiment with the different visualization types to find the one that best suits your needs.

Common Power BI visualization types:

- **Bar and column** - Various bar and column chart visualizations that present specific data across different categories in a stacked or clustered format.
- **Table** - A grid that contains related data in a logical series of rows and columns.
- **Line and area** - Help present trends over time.
- **Pie and donut** - Divide the data into segments.
- **Treemap** - Displays data as a set of nested rectangles. A colored rectangle (branch) containing smaller rectangles (leaves) represents each level of the hierarchy.
- **Waterfall** - Shows a running total as values are added or subtracted, which is useful in displaying a series of positive and negative changes.
- **Scatter** - Effective when comparing large numbers of data points without regard to time. You can add a play axis to animate how the data changes over time.
- **Map** - Geographic map with data shown as bubbles.
- **Card** - A single data point.
- **Gauge** - A circular arc that displays a single value that measures progress toward a goal or target.
- **Analytics** - Help you track progress toward a specific goal over time.

The quick insights feature generates visualizations based on your data. Power BI applies a set of sophisticated algorithms to discover potentially interesting trends and patterns and then generates visuals that you use.

![Diagram Dataverse Power BI report option.](../media/3-power-bi-insights.png)

Some AI powered visualizations that a solution architect should consider include:

- **Q&A** - Allows users to ask natural language questions and get answers in the form of a visual.
- **Key influencers** - Helps you understand the factors that are affecting a specific metric. It analyzes your data for you, ranks the factors that matter, and then displays those factors as key influencers. The visual also helps you contrast the relative importance of these factors.
- **Decomposition tree** - Automatically aggregates data and lets you drill down into your dimensions so that you can view your data across multiple dimensions. The decomposition tree can be used to conduct root cause analysis.

A common method for sharing Power BI visualizations is to create a Power BI app. Apps can be shared internally and externally. Power BI apps can be embedded in other applications. You can see an embedded Power BI app on the **Analytics** tab in Microsoft Power Platform admin center.

## Work with Dataverse data

Two options for using Dataverse data in Power BI are:

- **Common Data Service (legacy) connector** - The earlier version of the connector that uses the OData connection to Dataverse. You should use this connector for large datasets that are greater than 80 MB. This version also supports paging of the query results and building reports that use the image data type. OData connections import data into a dataset and are refreshed on a regular interval.
- **Dataverse connector** - This option uses the Tabular Data Stream (TDS) protocol to connect to Dataverse. This connector can either import the data into the dataset or use Direct Query, which permits real-time data.

> [!NOTE]
> You can also use dataflows, which are described later in this module.

The process for creating Power BI visualizations is shown in the following diagram.

![Diagram of Dataverse reporting options in various apps.](../media/3-process.png)

After you've connected to a Dataverse environment, perform the following series of activities to prepare and model the data:

- Select tables
- Set fields as the right data type
- Filter data
- Clean and transform data
- Manage relationships
- Use Data Analysis Expressions (DAX) to create analytics

Cleanup and transformation are required because it helps make data consumption easier. For instance, the dataset is easier for others to consume if you perform cleanup and transformation in your dataset by:

- Providing column names
- Using labels for choice columns
- Using lookup data
- Handling dates

## Handle dates

Power BI uses dates in visualizations extensively. Power BI automatically recognizes data columns and creates hierarchies by week, month, and year. You can use these hierarchies as standard. However, the solution architect should consider the creation of a date, calendar, or table, and then link dates to this table. This approach is a best practice in Power BI. A date table creates a row for every date within a range.

A calendar table will:

- Allow visuals to show zero values when no data is provided for a date.
- Provide more options for slicing and sorting data according to dates.
- Permit different granularity. For instance, it allows a comparison between a table that is based on month with another table based on days.
- Provide more options for using DAX date formulas. The SAMEPERIODLASTYEAR or LASTQUARTER type calculations don't work without a date table.
- Allow weekends and holidays to be excluded from calculations.

> [!IMPORTANT]
> Dates in Dataverse are stored in Coordinated Universal Time (UTC).

## Security

When using Power BI, you need understand how security on rows is applied. Power BI manages the security model. The Dataverse security model with security roles and business unit hierarchy doesn't apply on data that's imported into a Power BI dataset.

Power BI uses the concept of row-level security (RLS) to restrict data access for given users. Filters restrict data access at the row level, and you can define filters within roles. RLS is configured in Power BI desktop by using rules.

![Screenshot showing the Row Level Security.](../media/3-row-level-security.png)

Characteristics of row-level security are that it:

- Allows different levels of access for different users to the same content.
- Is based on DAX formulas.
- Applies security logic at *row level*.
- Is a True/False DAX evaluation for each row.

> [!NOTE]
> If you use the TDS endpoint with Direct Query, then the Dataverse security model is applied to data in Power BI.

## Alerts

Power BI can generate alerts from three visuals: gauge, card, and analytics on a Power BI dashboard. In Power BI service, a rule is added that specifies the threshold for the value and how often it's checked. A notification is triggered every time that the condition is met.

Alerts show in Power BI service, display on the Power BI mobile app, send by email, and optionally can trigger a Power Automate cloud flow.

## Workspaces vs. environments

Power BI doesn't use Microsoft Power Platform environments. Power BI uses workspaces to create separate spaces for datasets, reports, and dashboards. Workspaces are similar to environments. Users can be given roles in a workspace to allow collaboration when building Power BI components. A user doesn't need to belong to a workspace to have a report or dashboard shared with them.

## Application lifecycle management

Power BI resources can't be included in Microsoft Power Platform solution packages, and deployment needs to be managed separately.

Power BI has its own application lifecycle management (ALM) process (available with Power BI Premium only) to move Power BI components from one workspace to another.

The three stages of the ALM process are:

- **Development** - Design, build, and upload new content with fellow creators. This stage is first in deployment pipelines.
- **Test** - Test your app to see how it looks for your users with larger volumes of data.
- **Production** - Share the final version of your content with business users across the organization.
