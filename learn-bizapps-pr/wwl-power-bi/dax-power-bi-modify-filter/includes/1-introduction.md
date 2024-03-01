Watch the following video to learn about filter context.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4AvVc]

Filter context describes the filters that are applied during the evaluation of a measure or measure expression. Filters can be applied directly to columns, like a filter on the **Fiscal Year** column in the **Date** table for the value **FY2020**. Additionally, filters can be applied indirectly, which happens when model relationships propagate filters to other tables. For example, the **Sales** table receives a filter through its relationship with the **Date** table, filtering the **Sales** table rows to those with an **OrderDateKey** column value in **FY2020**.

> [!NOTE]
> Calculated tables and calculated columns aren't evaluated within filter context. Calculated columns are evaluated in row context, though the formula can transition the row context to filter context, if it needs to summarize model data. Context transition is described in Unit 5.

At report design time, filters are applied in the **Filters** pane or to report visuals. The slicer visual is an example of a visual whose only purpose is to filter the report page (and other pages when it's configured as a synced slicer). Report visuals, which perform grouping, also apply filters. They're implied filters; the difference is that the filter result is visible in the visual. For example, a stacked column chart visual can filter by fiscal year FY2020, group by month, and summarize sales amount. The fiscal year filter isn't visible in the visual result, yet the grouping, which results in a column for each month, behaves as a filter.

> [!div class="mx-imgBorder"]
> [![An image shows a report page with a slicer on Fiscal Year and a column chart visual for Sales Amount by Month.](../media/dax-filter-group-visual-ss.png)](../media/dax-filter-group-visual-ss.png#lightbox)

Not all filters are applied at report design time. Filters can be added when a report user interacts with the report. They can modify filter settings in the **Filters** pane, and they can cross-filter or cross-highlight visuals by selecting visual elements like columns, bars, or pie chart segments. These interactions apply additional filters to report page visuals (unless interactions have been disabled).

It's important to understand how filter context works. It guides you in defining the correct formula for your calculations. As you write more complex formulas, you'll identify times when you need to add, modify, or remove filters to achieve the desired result.

Consider an example that requires your formula to modify the filter context. Your objective is to produce a report visual that shows each sales region together with its revenue and revenue *as a percentage of total revenue*.

> [!div class="mx-imgBorder"]
> [![An image shows a table with three columns: Region, Revenue, and Revenue % Total Region. The table displays 10 rows and a total.](../media/dax-table-region-ratio-over-total-region-ss.png)](../media/dax-table-region-ratio-over-total-region-ss.png#lightbox)

The **Revenue % Total Region** result is achieved by defining a measure expression that's the ratio of revenue divided by revenue *for all regions*. Therefore, for Australia, the ratio is 10,655,335.96 dollars divided by 109,809,274.20 dollars, which is 9.7 percent.

The numerator expression doesn't need to modify filter context; it should use the current filter context (a visual that groups by region applies a filter for that region). The denominator expression, however, needs to remove any region filters to achieve the result for all regions.

> [!TIP]
> The key to writing complex measures is mastering these concepts:
>
> - Understanding how filter context works.
> - Understanding when and how to modify or remove filters to achieve a required result.
> - Composing a formula to accurately and efficiently modify filter context.
>
> Mastering these concepts takes practice and time. Rarely will students understand the concepts from the beginning of training. Therefore, be patient and persevere with the theory and activities. We recommend that you repeat this module at a later time to help reinforce key lessons.

The next unit introduces the [`CALCULATE`](/dax/calculate-function-dax/?azure-portal=true) DAX function. It's one of the most powerful DAX functions, allowing you to modify filter context when your formulas are evaluated.
