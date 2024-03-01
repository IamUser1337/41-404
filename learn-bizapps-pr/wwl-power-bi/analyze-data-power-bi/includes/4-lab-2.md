<!---TODO: Remove 
## Learning objectives

At the end of lab, you will be able to perform the following tasks: 
- Install a power BI app
- Filter a Power BI dashboard
- Analyze the data that makes up a visual
- Sort data and apply cross-filtering to a report

Estimated time to finish this lab: 20 to 30 minutes
---->

## Scenario

Congratulations. You are the new sales manager at a clothing manufacturing company named *Van Arsdel*. Your first assignment is to analyze your sales and marketing data to find why there is an unexpected dip in June sales. 

## Procedure

### Add the Sales and Marketing Sample app

> [!NOTE]
> If you already have the **Sales and Marketing sample** app installed, please skip to the next section.

1. Sign in to [http://app.powerbi.com](http://app.powerbi.com).
1. Select the **Apps** tab on the left.
1. Select the **Get apps** button.
1. Search for “_Retail Analysis_.”  

   ![Screenshot of the sample app for this lab.](../media/lab-2/power-bi-top-app-results.png)

1. Select the “**Get it now**” link and wait for the app to install.
1. From the **Install this Power BI app?** prompt, select the **Install** button.
1. From the **Get started with your new app** screen, select the **Explore App** button. 
1. Select the **Apps** tab on the left and then select the **Sales and Marketing sample** app tile.
1. The first time you launch the app, you will see **Get started with your new app**
1. Select the **Explore app** button to explore the dashboard.

 ### Apply a filter to a report page

In this section, you will explore two questions:

*  Why did our company, VanArsdel, underperform in June?
*  What are our best growth opportunities?

1. In the **Sales and Marketing sample** app, start on the **YTD Category** report page by selecting the **YTD Category** tab at the left of the screen.

   ![Screenshot of the YTD Category report in the sample app.](../media/lab-2/power-bi-ytd-category-report.png)

1. Notice the anomaly in the **Total Units by Month and Manufacturer** chart. 

   ![Screenshot of a dip for Van Arsdel only in June.](../media/lab-2/power-bi-june-dip.png)

1. If it is not already open, open the Filters pane by selecting **Filters** from the right side of your report.

1. Power BI displays all filters that the report designer applied to that visual.

   ![Screenshot of available filters for the visual.](../media/lab-2/power-bi-lab-filters.png)

1. The report designer filtered for Van Arsdel and our top three competitors and for the year 2014. That is good but she also filtered for the *Central region* and you want to see all of the regions. Clear the **Region** filter by clicking the eraser icon on that filter.

   ![Screenshot of the Region filter cleared by the eraser icon.](../media/lab-2/power-bi-region-filter.png)

1. Mouse over the **Total Units YTD by Manufacturer and Region** and note which segments in which Van Arsdel competes. Note that we compete in *Moderation* and *Convenience*.

   ![Screenshot of the Total Units YTD by Manufacturer and Region details.](../media/lab-2/power-bi-hover-1.png)

1. Hover over our competitors to see segments in which they compete. Do you see any patterns?

   ![Screenshot of the competitors details to see which segments they compete.](../media/lab-2/power-bi-hover-2.png)

1. Explore the same question just for the month of June. To cross-filter this report page for June, in the **Total Units by Month and Manufacturer** visual, click on the label **June-14**. Notice that all of the visuals in this report page update for June. 

   ![Screenshot of the cross-filter for the month of June.](../media/lab-2/power-bi-crossfilter-for-june.png)

1. Notice the cross-highlighting of the **Total Units YTD by Manufacturer and Region** visual. 

   ![Screenshot of cross-filter on Total Units YTD visual.](../media/lab-2/power-bi-visual-crossfilter-highlights.png)

1. Hover over each company to see the pattern of segments during June.

1. What can you conclude about the two most successful segments in June and why are our total sales dipping during that time?

1. To explore the same question in a different way: go to the **Growth Opportunities** report by selecting the **Growth Opportunities** tab.

1. Hover over the **Total Units by Segment** bar chart visual and then select the "Drill Up" icon (the up arrow) to see "Total Units by Manufacturer". 

   ![Screenshot of the Drill Up icon to see total units by manufacturer.](../media/lab-2/power-bi-filter-up-icon.png)

1. Clear the **isVanArsdel** and the **Segment** filters by clicking the eraser icons. This will allow us to see all of the companies and segments. Notice that Van Arsdel is the leading manufacturer overall. 

   ![Screenshot of the unfiltered Total Units by Segment visual.](../media/lab-2/power-bi-total-units-manufacturer.png)

1. Cross-filter for June on the **Total Units and Total Units by R12Ms by Month** visual by selecting **June-14**. Notice once again how Van Arsdel did in June.

   ![Screenshot of the cross-filtered view of sales in June.](../media/lab-2/power-bi-crossfilter-june-total-units.png)

1. Drill down to view segments in June by clicking the "Click to turn on Drill Down" icon and then the "Go to the next level in the hierarchy" icon. 

   ![Screenshot of the drill down icons in multiple hierarchy levels.](../media/lab-2/power-bi-drilldown.png)

1. Once again, what segments are the most successful in June.

   ![Screenshot of the units by segment for June.](../media/lab-2/power-bi-segments-in-june.png)

1. Why are Van Arsdel sales failing in June? What could we do to better compete? 
