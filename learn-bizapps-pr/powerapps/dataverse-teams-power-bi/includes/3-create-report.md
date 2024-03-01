Previously, you connected to your Dataverse for Teams table data and then transformed it. Now, you can build a report with interactive visualizations by using the **Report** view in Power BI, which consists of the following areas:

- **Report canvas** - Where visualizations are created and arranged (number **1** in the image).

- **Filters pane** - This allows you to filter and only work with subsets of data (number **2** in the image).

- **Visualizations pane** - Where you can select and edit the visualizations (number **3** in the image).

- **Fields pane** - Where you can choose the data to include in the visualizations or include it as a filter (number **4** in the image).

- **Pages tab** - Where you can create more report canvases (number **5** in the image).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Power BI Desktop with the report view items numbered.](../media/image-16.png)](../media/image-16.png#lightbox)

The basic steps to add visualizations to the report are:

1. Select a visualization from the **Visualizations** pane.

1. Select and drag the required fields from the **Fields** pane into the **Visualizations** pane or **Filters** pane.

1. Move and resize the visualization in the report canvas.

1. Make more edits to the visualization in the **Visualizations** pane.

## Add a stacked column chart

To add a stacked column chart, follow these steps:

1. Select the **Stacked Column Chart** icon from the **Visualizations** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane.](../media/image-17.png)](../media/image-17.png#lightbox)

1. Select and drag the following elements from the **Fields** pane:

    - **Date** field to **Axis**
    - **Total Cost** field to **Values**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations and Fields panes with Date dragged to Axis and Total Cost dragged to Values.](../media/image-18.png)](../media/image-18.png#lightbox)

1. Notice that the chart is showing the data by years. You can drill in to see the data by quarter and month by selecting the **Go to the next level in the hierarchy** icon. In the next step, you will edit the chart to show the data by month.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the chart with the "Go to the next level in the hierarchy" icon highlighted.](../media/image-19.png)](../media/image-19.png#lightbox)

1. With the chart selected in the report canvas, remove **Year** and **Quarter** under **Axis** so that the graph shows the data by month.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the chart with the date showing only month and day underneath Axis.](../media/image-20.png)](../media/image-20.png#lightbox)

1. Resize the chart in the report canvas by selecting and dragging the indicated border controls. Have the chart fill up the upper-left portion of the canvas.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the chart with the lower-right corner border control selected.](../media/image-21.png)](../media/image-21.png#lightbox)

## Add a line chart

To add a line chart, follow these steps:

1. Select the **Line Chart** icon in the **Visualizations** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane with the Line Chart icon highlighted.](../media/image-22.png)](../media/image-22.png#lightbox)

    > [!NOTE]
    > If you already have a visualization selected in the report canvas, then selecting another visualization will replace it. Make sure that you don't have a visualization selected by selecting a blank area of the report canvas before you create a new one.

1. Select and drag the following entities from the **Fields** pane.

    For **Axis**:
    - Date (remove Year and Quarter)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Axis section with Year and Quarter removed, leaving Month and Day.](../media/image-23.png)](../media/image-23.png#lightbox)

    For **Values**:
    - Materials
    - Printing
    - Assembly
    - Shipping

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Values section with the values added.](../media/image-24.png)](../media/image-24.png#lightbox)

1. Select and drag to resize the line chart to cover the lower half of the report canvas.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the charts with the line chart covering the lower half of the canvas.](../media/image-25.png)](../media/image-25.png#lightbox)

1. Change the data colors by going to the **Visualizations** pane, selecting the **Format** tab, and then expanding **Data colors**. Use the drop-down list next to each color and select the following theme colors:

    - **Materials** - Theme color 4
    - **Printing** - Theme color 5
    - **Assembly** - Theme color 6
    - **Shipping** - Theme color 3

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane with the Format tab icon selected and Data colors highlighted.](../media/image-26.png)](../media/image-26.png#lightbox)

## Add a stacked area chart

To add a stacked area chart, follow these steps:

1. Select the **Stacked Area Chart** icon in the **Visualizations** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane with the stacked area chart icon highlighted.](../media/image-27.png)](../media/image-27.png#lightbox)

1. Select and drag the following entities from the **Fields** pane to the **Values** area.

    For **Axis**:
    - Date (Remove Year and Quarter)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Axis area showing the date with Year and Quarter removed.](../media/image-28.png)](../media/image-28.png#lightbox)

    For **Values**:
    - Total Production Cost
    - Shipping

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Values area with the two fields added.](../media/image-29.png)](../media/image-29.png#lightbox)

1. Change the colors of the area chart to make it consistent with the rest of the report. In the **Visualizations** pane, select the **Format** tab and then expand **Data colors**. Use the drop-down list next to each color and select the following theme colors:

    - **Total Production Cost** - Theme color 2
    - **Shipping** - Theme color 3

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Format tab with data colors selected.](../media/image-30.png)](../media/image-30.png#lightbox)

1. If the new chart has automatically set the Y axis to zoom in on the shipping data, in the **Format** tab expand the **Y Axis** section and type in **0** for the start. The graph now shows both the Total Production Cost and the Shipping information.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the report stacked area chart with the Y axis set automatically, then the Y axis configuration under Format, then the chart with the Y axis set to start at zero.](../media/image-64.png)](../media/image-64.png#lightbox)

1. Select and resize the chart in the report canvas to occupy the existing space.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the report canvas with the stacked area chart filling the upper-right section of the report.](../media/image-31.png)](../media/image-31.png#lightbox)

## Change data to use currency format

Notice that the report shows data in the legends and pop-out windows as simple numbers without formatting. It would be more useful to have the data appear as currency.

> [!div class="mx-imgBorder"]
> [![Screenshot of the report with unformatted numbers.](../media/image-32.png)](../media/image-32.png#lightbox)

To change to currency format, follow these steps:

1. Under the **Fields** pane, select the **Assembly** field.

1. In the **Column tools** ribbon, select the **Currency** format icon.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Column tools tab in Power BI Desktop with the Currency icon highlighted.](../media/image-33.png)](../media/image-33.png#lightbox)

1. Repeat these steps for **Materials**, **Printing**, **Shipping**, **Total Cost**, and **Total Production Cost**.

After you have completed these steps, your data will appear as currency.

> [!div class="mx-imgBorder"]
> [![Screenshot of the report with numbers formatted as currency.](../media/image-34.png)](../media/image-34.png#lightbox)

## Explore the report

Power BI links your charts to be interactive when selecting a visual in one chart; the other charts will automatically adjust. For example, if you click on the data point for March under **Total Production Cost and Shipping by Month**, the other two charts will adjust to show data for that month. **Total Cost by Month** will highlight the data for March while the **Materials, Printing, Assembly, and Shipping by Month** line graph shows just the data point for March. Click on the same data point to revert all the charts back to normal.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Contoso Cost Trends report with March data selected in the Total Production Cost and Shipping by Month chart.](../media/image-65.png)](../media/image-65.png#lightbox)

Experiment by selecting other visuals in the other charts. As you add additional tables into your reports, you will create more complex reports that automatically interact to help you and your users explore the data. For more information on Power BI visual interactions and how to configure them, please see the links that are provided in the Summary section at the end of the module.

## Save the report

Save the report by selecting **File > Save as** in the menu. Enter **Contoso Cost Trends** as a name and then select **Save**. Power BI Desktop uses a **pbix** file extension for its saved files.

The final report should look similar to the following image.

> [!div class="mx-imgBorder"]
> [![Screenshot of the final Contoso Cost Trends report.](../media/image-35.png)](../media/image-35.png#lightbox)
