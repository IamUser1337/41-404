With Power BI Desktop, you can use the Power Query Editor tool to combine data from multiple sources into a single report. 

In this unit, you will combine data from different sources by using Query Editor.

![This page covers, "Combine data from different sources with Query Editor".](../media/05-power-bi-desktop-task-overview.png)

&nbsp;


## Add more data sources

To add more sources to an existing report, from the Home ribbon, select **Transform data** and then select **New Source**. You can use many potential data sources in Power BI Desktop, including folders. By connecting to a folder, you can import data from multiple Excel or CSV files at once. 

Power Query Editor allows you to apply filters to your data. For example, selecting the drop-down arrow next to a column opens a checklist of text filters. Using a filter allows you to remove values from your model before the data is loaded into Power BI.

![Screenshot of the "Remove Empty" option.](../media/05-power-bi-desktop-query-editor-filter.png)

> [!IMPORTANT]
> Filtering in the Power Query Editor changes which data is loaded into Power BI. Later, when you apply filters in the Data View or Report View, those filters only apply to what you see in visuals but do not change the underlying dataset.

### Merge and append queries

You can also merge and append queries. In other words, Power BI pulls data that you select from multiple tables or various files into a single table. Use the Append Queries tool to add the data from a new table to an existing query. Power BI Desktop attempts to match the columns in your queries, which you can then adjust as necessary in Power Query Editor.

![Screenshot of the Append Queries button and dialog.](../media/05-power-bi-desktop-append-queries.png)

### Write customized queries

You can use the Add Custom Column tool to write new customized query expressions by using the powerful M language.

![Screenshot of the Custom Column button and dialog.](../media/05-power-bi-desktop-custom-column.png)

For more information, see [Tutorial: Shape and combine data in Power BI Desktop](/power-bi/connect-data/desktop-shape-and-combine-data?azure-portal=true).
