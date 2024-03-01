There are a few differences in Power Query between Excel and Power BI. The data connectors and transformations available within Excel's Power Query are also available with Power BI's Power Query. 

In Power BI, the Power Query ribbon menu also includes [**AI Insights**](/power-bi/transform-model/desktop-ai-insights). Power BI offers some advanced features such as Python and R support that Excel does not.

## Power Query import from Excel

Excel and Power BI follow a similar data import process.

### Excel Power Query import

On the **Data** tab of the Excel ribbon, use the **Get Data** dropdown list; select **From File**; select **From Workbook**. This will launch a Windows Explorer window. Navigate to the folder where the source data is stored and select the workbook.

:::image type="content" source="../media/excel-get-data.png" alt-text="Screenshot of the get data menu with from file workbook selected.":::

### Power BI Power Query import

On the **Home** tab of the Power BI ribbon, use the **Get data** dropdown list; select **Excel**.

:::image type="content" source="../media/power-bi-get-data.png" alt-text="Screenshot of the get data menu with excel selected.":::

In both applications, you can accomplish the same outcome. You can connect to your data sources wherever they might be.

## Power Query: transform data

Most data sources need to be transformed after they're loaded into Excel or Power BI. You make these transformations and edits using the Power Query editor. Creating solutions using Power Query is an iterative process, because data sources and business questions change and evolve over time. In the following screenshot, you see the Power Query user interface (UI) in Excel (left) and in Power BI (right).

There are two options to launch the Power Query editor in Excel:

-   You can use the **Data** tab of the ribbon; **Get Data** dropdown list button; Launch Power Query Editor.

-   You can open the Queries and Connections pane using the **Queries and Connections** button on the **Data** tab. Right-click and choose the Edit option to launch the Power Query Editor window.

To launch the Power Query editor in Power BI Desktop, select the **Transform data** button on the **Home** tab on the ribbon.

:::image type="content" source="../media/power-query-editors.png" alt-text="Screenshot of Excel Power Query Editor on the left and Power BI Desktop Power Query Editor on the right." lightbox="../media/power-query-editors.png":::

The Power Query editors are nearly identical, as described at the beginning of this unit. You have the same functionality regardless of which application launched the editor.

>[!NOTE]
>Power Query also exists in the Power BI Service as **dataflows** to empower reuse of clean and transformed data for enterprise solutioning.