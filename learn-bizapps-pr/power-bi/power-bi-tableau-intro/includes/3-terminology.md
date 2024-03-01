## Visualization terminology

Regarding visualizations, Tableau analysts are familiar with Tableau sheets, dashboards, and workbooks. Analysts use these components when building a report in Tableau Desktop. The functionality of Tableau and Power BI is the same, though some entities are named differently in Power BI.

| | **Page** |**Visualization** |**Report** |**Dashboard** |
|--|--|--|--|--|
| **Definition** | Blank canvas for your visualizations and reports | A single graph, chart, or table; selected from the **Visualization** pane | Collection of visualizations in a single Power BI file | Collection of Power BI visualizations that are pinned onto a single view on Power BI service |
| **Tableau equivalent** | Sheet |  Visualization |Tableau Workbook/Dashboard | No Tableau equivalent |

## Data connection types

Tableau has two connection types: live connections and extracts. Both types have specific uses. Though one type is not better than the other, their use is dependent on the use case and its requirements. Live connections offer real-time analysis and use the resources that are invested on data sources, while extracts are snapshots of data that are optimized for aggregation and loaded into system memory to be quickly recalled for visualization.

The functionality of Tableau and Power BI connection types offer the same benefits; however, they're named differently in Power BI.

| | **Import mode** | **DirectQuery mode** |
|--|--|--|
| **Definition** | Delivers fast performance by importing the data, loading it into memory, and storing it to disk. | Allows analysts to query the data source on request to return results. |
| **Tableau equivalent** | Extracts | Live connection |
