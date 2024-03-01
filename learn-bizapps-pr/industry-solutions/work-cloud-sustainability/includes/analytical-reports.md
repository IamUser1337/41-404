Analytics reports present your calculated emissions in an organized way so that you can detect trends or explore your data. These reports are updated soon after your calculations are run, and you can review the outcome of your calculations in an aggregated format. You can also export data in predefined report formats that include groupings for emissions and activity and other dimensions.

For analytics and reporting, you’ll use Microsoft Power BI Embedded and Azure Data Lake. Currently, Sustainability Manager stores all analytical data in Azure Data Lake, and the Power BI interface is a managed Power BI. You can’t customize this storage option.  

Reports are refreshed periodically and automatically, so you don’t need to take action to do so. However, keep in mind that a few minutes will elapse between when you calculate emissions and when the impact is reflected in your reports.

The illustration below demonstrates the Emissions overview dashboard.
 
> [!div class="mx-imgBorder"]
> [![Screenshot representing analytics overview. When data was last refreshed, you can check in Insights.](../media/analytics-overview.png)](../media/analytics-overview.png#lightbox)

Two main levels of detail that you’ll find in the reports: 
- The Emissions Overview page includes a summary of your progress.
- Under Insights, you can explore your emissions data in greater detail. 

## Chart features

All charts are organized by source type, country/region, organization unit, facility, and the time. The illustration below shows the different features of charts.

> [!div class="mx-imgBorder"]
> [![Screenshot representing chart features where you can organize by source type, country/region, unit, facility and time.](../media/chart-features.png)](../media/chart-features.png#lightbox)
 
- **Interactive** - All charts are interactive. Essentially, you can select specific data and all related charts will filter based on your selection. This feature will help you understand your own data and find opportunities. 
- **Toggle** - Another design element is the toggles that you’ll find on some charts, such as toggles that show emissions breakdown by scope. Toggles give you flexibility to optimize the way that you visualize data analysis within a single chart.
- **Sorting** - Sorting is available on data grids to help you focus on the most important data that contributes to your emissions. For Scope 2 reports, you’ll find filters for location-based or market-based accounting methods.

## Insights

Insights screen allows you to conduct a more in-depth analysis of your data by scope. The tabs at the top of the screen will help you organize data based on scope, renewable energy, and deep analysis. For each scope type, data is organized by emission source, which you can explore by navigating through the tabs. 

- **Deep Analysis** - Deep analysis allows you more flexibility to explore your data by using the decomposition tree. You can drill down into your data by using dimensions, such as scope type, emission source facility, country/region, and organization. Additionally, you can enable the dimensions in any order that you want.

- **Reporting period** - To influence how insights are grouped, you can define a reporting period in the company profile. Also, this set influences the reports, which are available under **Reports**, where you can prepare to report different groupings of information.

    > [!Note]
    > Some organizations use the calendar year, while others will use fiscal year or an increment other than calendar year as a reporting period.

## Quantitative Preparation report

You can generate quantitative reports that extract emission and activity data from Microsoft Sustainability Manager. The reports are in an Excel format that can be used to submit the data to public disclosure organizations. 

There are two types of reports available – Emissions report and Activities report.

- **Emissions report** 
  The following fields are available:
    - Is market-based
    - Is biogenic
    - Scope
    - Emission source
    - Activity type
    
- **Activities report** 
  The available fields depend on the target activity that you selected.

    | Target activity       | Available fields        |
    |-----------------------|-------------------------|
    | Purchased energy      | Is renewable            |
    | Stationary combustion | Fuel type               |
    |                       | Industrial process type |
    | Mobile combustion     | Fuel type               |
    |                       | Vehicle type            |
    |                       | Industrial process type |
    | Industrial processes  | Facility                |
    |                       | Industrial process type |