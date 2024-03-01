In this unit, you explore the **Capture report views** showcase. This showcase demonstrates how to use the client APIs to apply and create bookmarks.

In the Power BI Embedded Analytics Playground menu, select the **Capture report views** showcase.

> [!div class="mx-imgBorder"]
> ![Image showing the Capture report views showcase highlighted.](../media/playground-capture-report-views-showcase.png)

In the embedded Power BI report, in the upper left, select the **Saved views** button.

> [!div class="mx-imgBorder"]
> ![Image highlighting the Saved views button.](../media/playground-capture-report-views-saved-views-button.png)

The list of *views* is actually bookmarks. The `bookmarksManager.getBookmarks` function has retrieved the report's bookmark collection.

Select any bookmark to apply it to the report, and then notice that the page updates with a new state. The `bookmarksManager.apply` function has applied the bookmark to the report.

In the **Manufacturer** slicer, select the first manufacturer, **Abbas**.

> [!div class="mx-imgBorder"]
> ![Image showing the Manufacturer slicer with Abbas selected.](../media/playground-capture-report-views-set-manufacturer-slicer.png)

Select the **Capture view** button.

> [!div class="mx-imgBorder"]
> ![Image highlighting the Capture view button.](../media/playground-capture-report-views-capture-view-button.png)

In the dialog window, beneath **Enter a name for this view**, enter **Abbas**.

> [!div class="mx-imgBorder"]
> ![Image showing the name Abbas being entered.](../media/playground-capture-report-views-capture-view-enter-name.png)

Select **Save**. The `bookmarksManager.capture` function has created a personal bookmark.

Return to the saved views, where the Abbas bookmark appears at the bottom of the list.

> [!div class="mx-imgBorder"]
> ![Image highlighting the Abbas bookmark in the Saved views list.](../media/playground-capture-report-views-saved-views-abbas.png)

For more information, see [Capture report views showcase](/javascript/api/overview/powerbi/showcase-bookmarks/?azure-portal=true).
