This exercise goes through the steps that Reed takes to ingest the spreadsheets that Alex provided. Data import is a vital task for bringing large volumes of data into Microsoft Sustainability Manager. This exercise uses Excel; however, many prebuilt connectors are available, and partners can build custom connectors to integrate with more data sources.

> [!IMPORTANT]
> To download the sample Excel files to ingest into Microsoft Sustainability Manager, go to [water sample data](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/sustainability-cloud/Water%20Sample%20Data.zip). In the GitHub page that appears, select the **Download** button. Extract the two Excel files to a folder on your local computer for use in this exercise.

## Import sample water data
To open sample water data, follow these steps:

1. Open a browser in an InPrivate or Incognito window and then go to [Microsoft Power Apps](https://make.powerapps.com/?azure-portal=true).

1. Select the environment from the **Environment** dropdown menu in the upper-right corner.

1. In the Power Apps portal, under **Apps** on the left navigation pane, open the **Sustainability Manager** application by selecting the play button.

   You're directed to the **Home** page for Microsoft Sustainability Manager.

Area navigation is a common first step in each exercise. The area navigation menu is in the lower-left corner of your screen.

> [!div class="mx-imgBorder"]
> [![Screenshot of the area navigation menu.](../media/area-navigation.png)](../media/area-navigation.png#lightbox)

## Import water quality data
Follow these steps to import water quality data:

1. In the change area, select **Data**.

1. Select **Data imports** from the navigation pane.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Data management section with Data imports highlighted.](../media/data-imports.png)](../media/data-imports.png#lightbox)

1. Select **New**.

1. Select **POWER QUERY GUIDED EXPERIENCE**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the options with Power Query Guided Experience highlighted.](../media/guided.png)](../media/guided.png#lightbox)

1. Select **Sources > Water**. Select **Add** next to **Water samples**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Define your data screen with Sources set to Water and with the Category name showing water quantity and quality data with the Add button for Water samples highlighted.](../media/water-add.png)](../media/water-add.png#lightbox)

1. Select **Next** after you add the data.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Define your data screen with data selected.](../media/define-data.png)](../media/define-data.png#lightbox)

1. Select **Excel workbook**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Choose data source screen showing Excel workbook as a new source.](../media/excel-workbook.png)](../media/excel-workbook.png#lightbox)

1. Select **Upload file**. Browse to the **Water Sample Data Wide World Importers 2022.xlsx** file saved on your system. Select **Open**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Connection settings section with Upload file selected.](../media/upload.png)](../media/upload.png#lightbox)

1. Select **Sign in** to sign in with your admin credentials.

1. After you upload the file and the connection is complete, select **Next**.

1. Select the **Water Sample Data** sheet and then select **Transform data**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Water Sample Data sheet loaded and the Transform data button highlighted.](../media/transform.png)](../media/transform.png#lightbox)

1. You can complete various data and column transformations on the **Transform data** page of the Power Query wizard. As a result, you can adjust data types, update column mappings, and perform advanced transformations that you're familiar with in Microsoft Power Platform dataflows or Microsoft Power BI datasets. Because you don't apply transformations in this exercise, select **Create**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Manage data source screen showing Queries and Query settings with the Create button highlighted.](../media/create.png)](../media/create.png#lightbox)

1. Go to the **New data connection** wizard on the **Schedule data import** page, where you complete the following actions:

   1. Turn on the **Import data automatically** toggle to allow the option for you to set a schedule for the data to be imported automatically. Selecting this option is beneficial if you use the connector in a scenario where the data changes frequently, such as a web API or FTP server.

   1. Turn on the **Replace previously imported data** toggle to remove all previously imported data and bring in the full dataset that was retrieved. Selecting this option is beneficial if the data source isn't providing data from only the last import or if it always includes a full set of data. For this scenario of importing historical data, leave both options turned off.

1. Select **Next** when you're finished.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Schedule data import area, showing the Next button.](../media/schedule.png)](../media/schedule.png#lightbox)

1. On the **Review and name** page, complete the following tasks:

   1. Enter a name for the new connection, such as **Water Sample Data**.

   1. Select **Connect**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Review and name area filled in and showing the Connect button.](../media/connect.png)](../media/connect.png#lightbox)

1. Map your source data to the data model. Data doesn't appear until this step is complete. Select **Map fields**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Map fields button on the You've completed the initial data setup screen.](../media/map-fields.png)](../media/map-fields.png#lightbox)

1. Select **Water samples** under **Data source**. Select **Auto map**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Mapping Water Sample Data screen with the Auto map button and the selected data source highlighted.](../media/auto-map.png)](../media/auto-map.png#lightbox)

1. Verify that the **Destination** and **Source** fields are mapped correctly. After reviewing your field mappings, switch the **Ready to import** toggle to **yes**. Select **Save**, select the **back arrow**, and then select **Done**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Mapping Water Sample Data screen with the Ready to import option set to yes and with the mapped fields and the Save button highlighted.](../media/mapping.png)](../media/mapping.png#lightbox)

1. On the **Data imports** screen, view the import that you created.

   The **Data import** job runs, and the status displays as **Scheduled**. In a moment, the status switches to **Processing**. You might need to refresh your page to view the change.

1. After a minute or two, select **Refresh** above the list to view the updated status, which should be **Complete**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Data imports showing status complete.](../media/imports.png)](../media/imports.png#lightbox)

1. Select **Water data** from the left navigation pane.

1. Select **Water samples** under **Water quality data**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Water data area with Water samples highlighted under Water quality data.](../media/water-sample.png)](../media/water-sample.png#lightbox)

1. Under **Organization**, filter by **Wide World Importers**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Organization expanded to show Filter By set to Equals Wide World Importers with the Apply button highlighted.](../media/organization.png)](../media/organization.png#lightbox)

After a few moments, the view refreshes and the activity data records that were imported during this exercise are displayed.

## Import water quantity data

This exercise goes through the steps that Reed takes to ingest the water quantity data for 2022 that Alex provided. This exercise uses Excel; however, many prebuilt connectors are available, and partners can build custom connectors to integrate with more data sources.

1. Select **Data imports** from the left navigation pane.

1. Select **New**.

1. Select **POWER QUERY GUIDED EXPERIENCE**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the options with Power Query Guided Experience highlighted again.](../media/guided.png)](../media/guided.png#lightbox)

1. Select **Add** next to **Water quantities**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Define your data screen with Water selected under Sources and Add selected next to Water quantities.](../media/add-quantity.png)](../media/add-quantity.png#lightbox)

1. After you select **Add**, select **Next**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Define your data screen with Water quantities selected and showing the Next button.](../media/quantities.png)](../media/quantities.png#lightbox)

1. Select **Excel workbook**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Choose data source screen, showing Excel workbook under New sources.](../media/excel-workbook.png)](../media/excel-workbook.png#lightbox)

1. Select **Upload file**. Browse to the **Water Quantity Data Wide World Importers 2022.xlsx** file saved on your system. Select **Open**.

1. Select **Sign in**, and you're signed in with your admin credentials.

1. After the file is uploaded and the connection is complete, select **Next**.

1. Select the **Water Quantity Data** sheet and then select **Transform data**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Choose data area, showing the Water Quantity Data sheet loaded and the Transform data button highlighted.](../media/transform-quantity.png)](../media/transform-quantity.png#lightbox)

1. You can complete various data and column transformations on the **Transform data** page of the Power Query wizard. As a result, you can adjust data types, update column mappings, and perform advanced transformations that you're familiar with in Microsoft Power Platform dataflows or Microsoft Power BI datasets. Because you don't apply transformations in this exercise, select **Create**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Manage data source screen, showing the Water Quantity Data query and the Create button.](../media/create-quantity.png)](../media/create-quantity.png#lightbox)

1. Go to the **New data connection** wizard on the **Schedule data import** page, where you complete the following actions:

   1. Turn on the **Import data automatically** toggle to allow the option for you to set a schedule for the data to be imported automatically. Selecting this option is beneficial if you use the connector in a scenario where the data changes frequently, such as a web API or FTP server.

   1. Turn on the **Replace previously imported data** toggle to remove all previously imported data and bring in the full dataset that was retrieved. Selecting this option is beneficial if the data source isn't providing data from only the last import or if it always includes a full set of data. For this scenario of importing historical data, leave both options turned off.

1. Select **Next** when you're finished.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Schedule data import, showing the two toggle options and the Next button.](../media/schedule.png)](../media/schedule.png#lightbox)

1. On the **Review and name** page, complete the following tasks:

   1. Enter a name for the new connection, such as **Water Quantities data**.

   1. Select **Connect**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Review and name page with the Name field filled in and the Connect button highlighted.](../media/connect-quantities.png)](../media/connect-quantities.png#lightbox)

1. Map your source data to the data model. Data doesn't appear until this step is complete. Select **Map fields**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Map fields button on the You've completed the initial data setup screen again.](../media/map-fields.png)](../media/map-fields.png#lightbox)

1. Select the **Data source** to map. For this exercise, select **Water quantities**. Select **Auto map**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Mapping Water Quantities Data page with Data source set to Water quantities and with the Auto map button highlighted.](../media/auto-map-quantities.png)](../media/auto-map-quantities.png#lightbox)

1. Verify that the **Destination** and **Source** fields are mapped correctly. Select **Save**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the mappings, showing Destination and Source fields and data types with the Save button highlighted.](../media/save-mapping.png)](../media/save-mapping.png#lightbox)

1. Select the **Ready to import** toggle and then select the back arrow.

1. Select **Done**.

1. On the **Data imports** page, view the import that you created.

   The **Data import** job runs, and the status displays as **Scheduled**. In a moment, the status switches to **Processing**. You might need to refresh your page to view the change.

1. After a minute or two, select **Refresh** above the list to view the updated status, which should be **Complete**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the refreshed list showing a status of Complete.](../media/status.png)](../media/status.png#lightbox)

1. Select **Water data** from the left navigation pane.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the navigation pane with Water data selected.](../media/water-data.png)](../media/water-data.png#lightbox)

1. Select **Water quantities** under **Water quantity data**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Water quantities selected under Water quantity data.](../media/water-quantities.png)](../media/water-quantities.png#lightbox)

1. Under **Organization**, filter by **Wide World Importers**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Organization menu expanded to show Filter By set to Equals Wide World Importers.](../media/organization.png)](../media/organization.png#lightbox)

After a few moments, the view refreshes and the activity data records that were imported during this exercise are displayed.

  > [!div class="mx-imgBorder"]
  > [![Screenshot of the All water quantities view refreshed to show imported records.](../media/all-water-quantities.png)](../media/all-water-quantities.png#lightbox)
