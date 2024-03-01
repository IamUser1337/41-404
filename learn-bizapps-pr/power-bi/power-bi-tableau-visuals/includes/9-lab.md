In this lab, create your first dashboard in Power BI using the standard visuals in Power BI, including the bar chart and scatter plot. Then add interactivity using cross filtering, bookmarks, and the Decomposition tree standard visual. At the end of this lab, you create a report like this one.

:::image type="content" source="../media/final-dashboard.png" alt-text="Screenshot of a Power BI dashboard leveraging standard visuals." lightbox="../media/final-dashboard.png":::

## Creating a dashboard

In this exercise, you create a dashboard and add interactivity.

### Task 1: Build a scatter chart

In this task, you create a scatter chart.

1. Create a new page by selecting the yellow "plus" sign at the bottom of the screen. Title this tab *Tailspin Toys*.

1. From the **Visualizations** panel, select the **Scatter chart** visual.

1. From **Data** section, drag and drop **Sales Amount** field from **Measures Table** table to **X Axis**.

1. From **Data** section, drag and drop **Quantity** field from **Sales** table to **Y Axis**.

1. From **Data** section, drag and drop **Product** field from **Product** table to **Details**.

   This action provides a representation of the **Quantity** and **Sales Amount** by **Product**.

### Task 2: Format the scatter chart

1. Select the **Format you visual** icon. Under **Visual**, select **Marker** to expand it. Under **Shape** set the **Size** to 7 and set the **Marker shape** to diamond.

   :::image type="content" source="../media/marker-shape.png" alt-text="Screenshot of the Marker shape dropdown menu selection.":::

1. Under **General**, select **Title** to expand it. Under **Title**, for **Text**, enter *What are my best selling products?* Set the **Font** size to 18.

1. *OPTIONAL* In the **Format** section, under **Background** set to Off.

   :::image type="content" source="../media/background-off.png" alt-text="Screenshot of Background set to Off in the Format section.":::

1. *OPTIONAL* In the **Format** section, under **Border** set the **Color** to White and the **Radius** to 20.

   :::image type="content" source="../media/format-border-color.png" alt-text="Screenshot of the Color set to white and Radius set to 20.":::

1. *OPTIONAL* In the **Format** section, under **X-axis**, go down to **Gridlines** and set the **Color** to White and the **Stroke width** to 4.

   :::image type="content" source="../media/format-gridlines.png" alt-text="Screenshot of the Color set to white and the Stroke width set to 4.":::

1. *OPTIONAL* In the **Format** section, under **Y-axis,** go down to **Gridlines** and set the **Color** to White and the **Stroke width** to 4.

### Task 3: Create a stacked bar chart

1. From the **Visualizations** panel, select the **Stacked bar chart** visual :::image type="icon" source="../media/stacked-bar-chart.png":::.

1. From the **Data** section, drag and drop **Sales Amount** field from **Measures Table** table to **Values**.

1. From the **Data** section, drag and drop **State** field from **Geography** table to **Axis**.

   This configuration provides a representation of the **Sales Amount** by **State**.

### Task 4: Format the stacked bar chart

1. Select the **Format you visual** icon. Under **Visual**, select **Bars** to expand it. Next to **Colors** > **Default** select :::image type="icon" source="../media/data-color-function.png":::.

   > [!NOTE]
   > From this screen notice that there are a number of different methods you can create conditional formatting including Color Scale, Rules, and Field value. No additional calculations are necessary to create conditional formatting.

1. In the **Default color** window, select **OK** to confirm your selections.

1. Under **Format visual**, select **General**. Select **Title** to expand it. For **Test**, enter *Where are my highest sales?* For **Font** size, select 18.

1. *OPTIONAL* In the **Format** section, under **Background** set to Off.

1. *OPTIONAL* In the **Format** section, under **Border** set the **Color** to White and the **Radius** to 20.

### Task 5: Create an area chart

1. From the **Visualizations** panel, select the **Area chart** visual :::image type="icon" source="../media/area-chart.png":::.

1. From the **Data** section, drag and drop the **Sales Amount** field from **Measure Table** to **X-axis**.

1. From the **Data** section, drag and drop the **Order Date** field from **Sales** to **Y-axis**.

1. From the **Visual Header**, select the drill-down button twice to show the chart by Year.

   :::image type="content" source="../media/drill-down.png" alt-text="Screenshot of the drill-down button on the Visual Header.":::

### Task 6: Format the area chart

1. Select the **Format your visual** icon. Select **X-axis** to expand it. Select the color selector box and select the light blue.

   :::image type="content" source="../media/color-selection-pane.png" alt-text="Screenshot of the color selector box with light blue selected.":::

1. Select **Title** to expand it. For **Title text**, enter *How have my sales changed over time?* Set the font size to **18**.

1. *OPTIONAL* In the **Format** section, under **Background** set to **Off**.

1. *OPTIONAL* In the **Format** section, under **Border** set the **Color** to White and the **Radius** to *20*.

### Task 7: Add a decomposition tree

1. From the **Visualizations** panel, select the **Decomposition tree** visual :::image type="icon" source="../media/decomposition-tree.png":::.

1. From the **Data** section, drag and drop the **Discount %** field from **Measure Table** to **Analyze**.

1. From the **Data** section, drag and drop the **ItemGroup** field from **Product** to **Explain by**.

1. From the **Data** section, drag and drop the **ProductCategory** field from **Product** to **Explain by**.

1. From the **Data** section, drag and drop the **Product** field from **Product** to **Explain by**.

1. Expand out the fields by selecting the "plus sign" next to each dimensional group.

### Task 8: Format decomposition tree

1. Select the **Format your visual** icon. Select **Tree** to expand it. In **Tree settings**, set **Density** to **Dense**.

1. Select **General** > **Title**. Turn the title **On** and enter the text *Where do my discounts go?* Set the font size to **18**.

1. *OPTIONAL* Under **Visual** > **Data bars** > **Colors**, set **Bar background** to white.

   :::image type="content" source="../media/data-bar-background-color.png" alt-text="Screenshot of the Data bars Bar background with Color set to white.":::

1. *OPTIONAL* Under **General** > **Effects**, set **Background** to **Off**.

### Task 9: Add a multi-row card

1. From the **Visualizations** panel, select **Multi-row card** visual :::image type="icon" source="../media/multi-row-card.png":::.

1. From the **Data** section, drag and drop **Sales Amount** from **Measures Table** to the **Fields**.

1. From the **Data** section, drag and drop **Quantity** field from **Sales** to the **Fields**.

1. From the **Data** section, drag and drop **Discount %** field from **Measures Table** to the **Fields**.

1. From the **Data** section, drag and drop **Discount Amount** field from **Sales** to the **Fields**.

### Task 10: Format multi-row card

1. *OPTIONAL* Select the **Format you visual** icon. Select **Visual** > **Callout values**. Set the **Font** size to 21 and the **Color** to white.

   :::image type="content" source="../media/data-labels.png" alt-text="Screenshot of Data Labels with Color set to white and Text Size set to 21.":::

1. *OPTIONAL* Select **Visual** > **Category labels**. Set the **Font** size to 14.

   :::image type="content" source="../media/category-labels.png" alt-text="Screenshot of Category Labels with Text size set to 14.":::

1. *OPTIONAL* Select **Visual** > **Cards** > **Style**, under **Background**, select white.

### Task 11: Set page background

1. *OPTIONAL* Select anywhere on the background of the **Page** to deselect visuals.

1. *OPTIONAL* Select the **Format your report page** icon. Under **Canvas background** > **Color** set the color to the lightest gray available and set **Transparency** to 0.

   :::image type="content" source="../media/page-background-color.png" alt-text="Screenshot of Page background Color set to light gray and Transparency set to 0.":::

### Task 12: Add a header (optional)

1. From the ribbon, under **Insert** > **Elements** > **Shapes**, select the **Rectangle** icon.

1. From **Format** > **General** > **Properties**, set the **Height** and **Width** and to be 120 and 1280 respectively.

1. From **Format** > **Shape** > **Style** > **Fill**, set the value to **Off**.

1. From **Format** > **Shape** > **Style** > **Border**, set the **Width** to **0**.

1. From **Format** > **General** > **Effects**, for **Background** select **On**.

1. Under **Background** > **Color**, select a medium gray.

   :::image type="content" source="../media/shape-format-background-color.png" alt-text="Screenshot of Background color set to medium gray.":::

### Task 13: Add a logo

1. From the ribbon, under **Insert** > **Elements**, select the **Image** icon. Navigate to the "Toys of Tomorrow Icon" and select **Open**.

### Task 14: Add page filters

1. Expand the **Filters** pane, if it's closed.

   :::image type="content" source="../media/expand-filters.png" alt-text="Screenshot of the Filters, Visualizations, and Fields panes.":::

1. From the **Data** section, drag and drop **KitType** field from **Product** to **Filters on this page**.

1. From the **Data** section, drag and drop **Region** field from **Geography** to **Filters on this page**.

### Task 15: Add cross filtering

1. Select on one of the visuals you've created.

1. From the ribbon, under **Format** > **Interactions**, select **Edit interactions**.

1. For each of the *other* visuals you've created, select the **Filter** icon from the **Visual Header**.

   :::image type="content" source="../media/apply-action-filter.png" alt-text="Screenshot of the Filter icon from the Visual Header.":::

1. Repeat the steps in this task with each of the others visuals you created.

### Task 16: Create two bookmark actions with icons

In this task, make a copy of the bar chart you've already made, convert it to a map, and give the user the option to pick between the two.

1. Select the bar chart you've already created. To copy and paste, select **Ctrl**+**C** and **Ctrl**+**P**.

1. Select the new copy of your bar chart and, from the **Visualizations** panel, select **Filled Map** visual :::image type="icon" source="../media/filled-map.png":::.

1. Place the bar chart and map that you've created on top of each other.

1. Open the **Selection Pane** and **Bookmarks Pane** by going to the **Ribbon** under **View** > **Show Panes** select **Selection Pane** and **Bookmarks Pane**.

1. From the **Selection Pane**, hide the map visual by selecting on the **Show/Hide** icon next to it. You know you've selected the correct visual by selecting on the name in the **Selection Pane** results in highlighting the visual in the report canvas.

1. Create your first bookmark by going to the **Bookmarks Pane** and selecting **Add**. Rename this bookmark to *Bar*.

1. Using the **Selection Pane**, unhide the map visual. Then hide the bar chart visual.

1. Create another bookmark by going to the **Bookmarks Pane** and selecting **Add**. Rename this bookmark to *Map*.

1. From the ribbon, under **Insert** > **Elements**, select the **Image** icon. Navigate to the "Map Icon" and select **Open**.

1. Select the "Map Icon" and, under the **Format image** section, set **Action** to On.

1. From **Format image** section, select **Action** > **Type** as "Bookmark" and select **Action** > **Bookmark** as "Map".

1. From the ribbon, under **Insert** > **Elements**, select the **Image** icon. Navigate to the "Bar Chart Icon" and select **Open**.

1. Select the "Bar Chart Icon" and, under the **Format image** section, set **Action** to On.

1. From **Format image** section, select **Action** > **Type** as "Bookmark" and select **Action** > **Bookmark** as "Bar".

   You can now **Ctrl**-select on either of these two icons to swap between the bar chart and map.

### Task 17: Arrange and style

Now that you have the building blocks, use the remaining time to arrange the visuals in a way that tells a story. Here's a couple of tips to get you going:

- From the ribbon, under **View** > **Themes**, pick a theme to set your colors and font. Then customize the theme to fit your style.

  :::image type="content" source="../media/themes-pane.png" alt-text="Screenshot of the Themes view with a theme selected to set colors and fonts." lightbox="../media/themes-pane.png":::

- Select anywhere on the empty canvas to reveal options to alter the size, color, or even insert an image into the background.

  :::image type="content" source="../media/format-pane.png" alt-text="Screenshot of menu to alter the size and color or add an image.":::

- **Ctrl**+select multiple items to format them at the same time.

In this lab, you created your first dashboard in Power BI using the standard visuals in Power BI, including the bar chart and scatter plot. You added interactivity using cross filtering, bookmarks, and the Decomposition tree standard visual.
