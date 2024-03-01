You can embed other types of Power BI content, including Power BI report visuals, paginated reports, dashboards, dashboard tiles, and the Q&A experience. Unlike Power BI reports, it's not possible to edit or create these other content types.

## Embed Power BI report visuals

You can embed single report visuals that are sourced from a Power BI report. Use a configuration object of type `IVisualLoadConfiguration`. In addition to the required properties (described in Unit 1; the `type` property is set to **visual**), you must also set the following properties.

- `pageName` - Required The name of the page that contains the visual that you're embedding. You can use the Report [getPages](/rest/api/power-bi/reports/getpages/?azure-portal=true) function to obtain the pages in the report.
- `visualName` - Required. The name of the visual that you're embedding. You can use the Page [getVisuals](/javascript/api/powerbi/powerbi-client/page.page?azure-portal=true#getVisuals__) function to obtain the visuals in a page.

Your app can apply filters to the visual by using the [updateFilters](/javascript/api/overview/powerbi/control-report-filters?azure-portal=true#update-filters) function.

> [!TIP]
> Don't embed too many visuals that are sourced from the same page because it may not perform well. Also, if you need more control when embedding several visuals from the same report, you can accomplish that more efficiently by using *custom layouts*. For more information about custom layouts, see [Personalize a report layout](/javascript/api/overview/powerbi/custom-layout/?azure-portal=true).

For a complete description of embedding Power BI report visuals, see [Embed a report visual](/javascript/api/overview/powerbi/embed-visual/?azure-portal=true).

## Embed paginated reports

You can embed paginated reports by using a configuration object of type `IEmbedConfigurationBase`. In addition to the required properties (described in Unit 1; the `type` property is set to **report**), you must also set the following properties.

- `id` - Required. The workspace ID (GroupID) that contains the paginated report.
- `uniqueId` - Required. The ReportID of the paginated report.

There's also the `settings` property, which is optional. You can pass an object of type `IPaginatedReportSettings` to specify information about the appearance of the report's parameter panel. Your app can enable and expand open the panel.

To set paginated report parameters, pass them in the embed URL. However, it's not possible to set multi-parameter values. For more information, see [Pass a report parameter in a URL for a paginated report in Power BI](/power-bi/paginated-reports/report-builder-url-pass-parameters/?azure-portal=true).

For a complete description of embedding paginated reports, see [Embed a paginated report](/javascript/api/overview/powerbi/embed-paginated-report/?azure-portal=true).

## Embed dashboards

You can embed dashboards by using a configuration object of type `IDashboardLoadConfiguration`. In addition to the required properties (described in Unit 1; the `type` property is set to **dashboard**), you can also set the `pageView` property. Options include:

- `fitToWidth` - The embedded dashboard's width matches the width of the `div` element that contains the dashboard.
- `oneColumn` - The embedded dashboard appears in one column. This option is suited to small form factor devices, like a mobile phone.
- `actualSize` - The embedded dashboard appears at full size.

For a complete description of embedding dashboards, see [Embed a dashboard](/javascript/api/overview/powerbi/embed-dashboard/?azure-portal=true).

## Embed dashboard tiles

You can embed dashboard tiles by using a configuration object of type `ITileLoadConfiguration`. In addition to the required properties (described in Unit 1; the `type` property is set to **tile**), you must also set the following properties.

- `dashboardId` - Required. The DashboardID of the dashboard that contains the tile.
- `id` - Required. The ID of the dashboard tile. You can use the Power BI REST API to obtain dashboard tiles and their properties.

For a complete description of embedding dashboard tiles, see [Embed a dashboard tile](/javascript/api/overview/powerbi/embed-dashboard-tile/?azure-portal=true).

## Embed the Q&A experience

You can embed the Q&A experience by using a configuration object of type `ILoadQnaConfiguration`. In addition to the required properties (described in Unit 1; the `type` property is set to **qna**), you should also set the following properties.

- `datasetIds` - Required. An array of DatasetIDs. However, only one DatasetID is currently supported.
- `viewMode` - Optional. Either `QnaMode.Interactive`, which allows the user to enter questions, or `QnaMode.ResultOnly`, which requires a supplied question.
- `question` - Optional. The question that your app supplies. The `viewMode` property must be set to `QnaMode.ResultOnly`.

> [!TIP]
> Encouraging the use of Q&A can help reduce the number of reports and dashboards that you need to develop. Also, you can embed a Q&A visual from a Power BI report. This approach provides the ability to format the visual, and the app can apply filters to it.

For a complete description of embedding the Q&A experience, see [Embed a standalone Q&A visual](/javascript/api/overview/powerbi/embed-q-and-a/?azure-portal=true).
