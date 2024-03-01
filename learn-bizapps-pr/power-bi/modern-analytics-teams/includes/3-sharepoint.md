Once you've published a report to the Power BI service, you can embed interactive Power BI reports in SharePoint Online pages. From the Power BI service report: Use the **File** menu, select **Embed** > **SharePoint Online** to get the URL.

> [!div class="mx-imgBorder"]
> [![Screenshot of more options menu, SharePoint Online, embed report.](../media/options-menu.png)](../media/options-menu.png#lightbox)

Then, from SharePoint Online, select **Pages** > **New** > **Site Page** > **Power BI** > **Add Report** and paste the URL. Select **Publish** to publish the report.

> [!div class="mx-imgBorder"]
> [![Screenshot of the SharePoint Online Publish button.](../media/publish-button.png)](../media/publish-button.png#lightbox)

## SharePoint Online search

SharePoint Online makes relevant reports easily accessible through its Search function, even without knowing the workspace to which the report is saved.

> [!div class="mx-imgBorder"]
> [![Screenshot of search on SharePoint.](../media/search.png)](../media/search.png#lightbox)

## SharePoint as a data source

Power BI has three standard connectors with SharePoint. You can connect to both SharePoint Online and on-premises SharePoint for Lists. SharePoint folder pulls all files included in the folder.

> [!div class="mx-imgBorder"]
> [![Screenshot of SharePoint Connector Options.](../media/connectors.png)](../media/connectors.png#lightbox)

It's important to note when utilizing the SharePoint folder connector, the M language query uses `SharePoint.Files()`. This function can cause slow refresh speeds due to the site metadata that loads with it. Updating the formula to use `SharePoint.Contents()` instead can provide a large boost to query-refresh speeds.
