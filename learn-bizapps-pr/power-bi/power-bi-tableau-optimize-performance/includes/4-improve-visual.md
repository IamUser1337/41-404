The number and type of visuals on your report have considerable impact on your report's performance, but several best practices and troubleshooting methods are available to help you improve this issue.

## Improve performance with the Filter pane

The **Filter** pane is beneficial in helping you organize your filters, but it's also a great way to improve performance. Each slicer acts like a visual; slicers are loaded and changed every time you make changes to a report. The **Filter** pane is only loaded when it's opened, so it can be kept off to the side until you need it.

## Limit the number of visuals

As with any program, the more you add to it, the slower it becomes. The same is true when you're building a report. We recommend that you keep to fewer than nine visuals for each page. This recommendation is easier to follow with the **Filter** pane.

## Test your external visual

When using visuals from other sources, you should always try to test them. Developers use the Power BI visuals SDK to create the Power BI custom visuals. The SDK is an open-source, command-line tool, which means that the code hasn't been developed in a controlled environment. Additionally, no support is available if something goes wrong with the visual.

Some visuals from other sources are high-performance, while others aren't. Make sure you review the visuals that you use for performance.

## Limit interactions

Similar to Tableau Desktop, the more interactions that occur in your reports in Power BI Desktop, the more you need to update when requirements and the data change.

## Use Performance Analyzer

In Power BI Desktop, you can find out how each of your report elements is performing with the built-in Performance Analyzer tool. With Performance Analyzer, you can see and record logs that measure how each of your report elements performs when users interact with them and which aspects of their performance are taking the most resources.
