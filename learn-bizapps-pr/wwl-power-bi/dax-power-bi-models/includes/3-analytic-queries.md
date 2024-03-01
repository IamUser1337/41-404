An *analytic query* is a query that produces a result from a semantic model. Each Power BI visual, in the background, submits an analytic query to Power BI to query the model. The analytic query is written as a Data Analysis Expressions (DAX) query statement. However, you don't need to write a native DAX statement; you only need to configure report visuals by mapping semantic model fields.

An analytic query has three phases that are implemented in the following order:

1. Filter
1. Group
1. Summarize

> [!div class="mx-imgBorder"]
> [![An animation shows the sequence of the three analytic query phases: Filter, Group, and Summarize.](../media/dax-filter-group-summarize-c.gif)](../media/dax-filter-group-summarize-c.gif#lightbox)

**Filtering**, or slicing, targets the data of relevance. In Power BI reports, filters can be applied to three different scopes: the entire report, a specific page, or a specific visual. Filtering is also applied in the background when row-level security (RLS) is enforced. Each report visual can inherit filters or have filters directly applied to it.

**Grouping**, or dicing, divides query results into groups.

**Summarizing** produces a single value result. Typically, numeric columns are summarized by using summarization methods (sum, count, and many others). These methods are simple summarizations. More complex summarizations, like a percent of grand total, can be achieved by defining measures that are written in DAX.

Not all analytic queries need to filter, group, and summarize:

- Commonly, report visuals are filtered, perhaps by a time period or geographic location.
- Grouping is optional. For example, a card visual, which is used to display a single value, isn't concerned with grouping.
- Typically, report visuals summarize. One notable exception, however, is the slicer visual, which isn't concerned with summarization.
