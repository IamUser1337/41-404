In this unit, you explore the **Go from insights to quick action** showcase. Contoso, a sales company, needs to send coupons or discount vouchers to specific customers. This showcase demonstrates how Contoso achieved that requirement by using event handling and visual data export.

In the Power BI Embedded Analytics Playground, in the left menu, select the **Home** icon to return to the home page.

> [!div class="mx-imgBorder"]
> ![Image showing the menu with the Home icon highlighted.](../media/playground-return-home.png)

If the browser prompts you about losing changes, select **OK**.

In the menu, select the first icon to expand the menu.

> [!div class="mx-imgBorder"]
> ![Image showing the menu with the Expand menu icon highlighted.](../media/playground-expand-open-menu.png)

In the menu, expand the **Showcases** group.

> [!div class="mx-imgBorder"]
> ![Image showing the menu with the Showcases group highlighted.](../media/playground-expand-open-showcases.png)

Select the **Go from insights to quick action** showcase.

> [!div class="mx-imgBorder"]
> ![Image showing the Go from insights to quick action showcase highlighted.](../media/playground-select-go-insights-quick-action-showcase.png)

The embedded Power BI report includes various slicers across the top and a table visual of customers beneath it. Use any slicer to filter the table visual so that it results in a small subset of customers.

Select the **Create a campaign** button.

> [!div class="mx-imgBorder"]
> ![Image showing the Create a campaign button.](../media/playground-go-insights-quick-action-create-campaign-button.png)

The report has raised the `buttonClicked` event and the app has responded by opening a dialog window. The dialog window used the `exportData` function to retrieve the customers from the report's table visual.

The dialog window allows users to optionally clear customers and then select **Send coupon** or **Send discount**. The app is responsible for recording and sending coupons or discount vouchers to the selected customers.

For more information, see [Go from insights to quick action showcase](/javascript/api/overview/powerbi/showcase-export-events/?azure-portal=true).
