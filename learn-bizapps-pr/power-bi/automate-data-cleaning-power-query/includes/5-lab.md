Now's your opportunity to give Power Query a try with this guided, step-by-step use case. Use the provided example data source files to complete the exercises.

## Lab 01 - Analytics in Excel: Use Power Query in Excel

The estimated time to complete this lab is 30 minutes.

In this hands-on learning lab, you'll complete the following tasks:

1. Use Power Query to connect to a .csv source data file - Customers
1. Use Power Query transformations to splice a column by delimiter - Customers
1. Use Power Query to connect to an Excel source data file - Quotes
1. Use Power Query transformations to unpivot - Quotes
1. Use Power Query transformations to clean - Quotes

## Lab prerequisites

The following prerequisites and setup must be in place to successfully complete the exercises:

- You must be connected to the internet.
- You must have Microsoft Office installed.
- Sign up for [Microsoft Power BI](https://aka.ms/pbimaiadtraining/?azure-portal=true).
- At a minimum, you should have a computer with two cores and 4 GB of RAM that is running Windows 8 or later or  Windows Server 2008 R2 or later.
- You can use Microsoft Edge or Google Chrome.
- Verify whether you have a 32-bit or 64-bit operating system to decide if you need to install the 32-bit or 64-bit applications.

  > [!NOTE]
  > 64-bit Excel and Power BI Desktop is best.

   > [!IMPORTANT]
   > Download the student content: Create a folder called **ANALYST-LABS** on the C: drive of your local machine. Download and extract all content from https://aka.ms/modern-analytics-labs to the ANALYST-LABS folder that you created (C:\ANALYST-LABS).
- Download and install Power BI Desktop by using any one of the following options:
  - If you have Windows 10 or later, use Microsoft App Store to download and install Power BI Desktop application.
  - Download and install [Microsoft Power BI Desktop](https://aka.ms/pbiSingleInstaller).
- If you already have Power BI Desktop installed, ensure that you have the latest version of Power BI downloaded.

## Document structure

Source data or starting files for each lab are located within each lab folder.

- You'll complete Lab 01 by using Power Query in the **Excel** application.

- You'll complete Lab 02A and Lab 02B by using **Power BI Desktop** application.

- You'll complete Lab 03A by using **Power BI Desktop**, **Power BI service**, and **Excel** applications.

- You'll complete Lab 03B by using **Excel** and **Power BI service** applications.

Each lab comes with step-by-step instructions to follow and contains screen images throughout the instructions. The key actions for each step are identified by **bold** text. Pay attention to notes, tips, and other important information. Each lab contains a completed solution file you can use as a reference.

## Overview

The estimated time to complete this lab is 30 minutes.
In this lab, you will complete the following tasks:

1. Use Power Query to connect to a CSV source data file - Customers
1. Use Power Query transformations to Split Column by Delimiter - Customers
1. Use Power Query to connect to an XLSX source data file - Quotes
1. Use Power Query transformations to Unpivot - Quotes
1. Use Power Query transformations to Clean - Quotes

    > [!NOTE]
    > This lab has been created based on the sales activities of the *fictitious* Wi-Fi company called SureWi, which has been provided by [P3 Adaptive](https://p3adaptive.com/?azure-portal=true). The data is property of P3 Adaptive and has been shared with the purpose of demonstrating Excel and Power BI functionality with industry sample data. Any use of this data must include this attribution to P3 Adaptive.

## Exercise 1: Use Power Query to connect to CSV - Customers.csv

In this exercise, you'll use Excel to connect to a CSV source data file.

### Task 1: Launch Excel

In this task, you'll launch a new blank worksheet to get started.

1. Launch Excel.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Excel logo.](../media/lab-excel-logo.png)](../media/lab-excel-logo.png#lightbox)

1. Create a new blank workbook.
    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New blank workbook selection screen in Excel.](../media/lab-create-workbook.png)](../media/lab-create-workbook.png#lightbox)

### Task 2: Use Power Query to connect to CSV

In this task, you'll connect to the Customers CSV source data file.

1. Select the **Data** tab on the main Excel ribbon.
1. Select **Get Data > From File > From Text/CSV**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Data > From Text/CSV menu option.](../media/lab-data-from-text-csv.png)](../media/lab-data-from-text-csv.png#lightbox)

1. Go to the **C:\ANALYST-LABS\Lab 01\MAIAD Lab 01 - Data Source - Customers.csv** file.

   The **Preview** area will display a sample of the customer's data, column names, and values.

    > [!NOTE]
    > This example is only a preview of the data.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Navigator window showing preview data from Lab 01 - Data Source - Customers.csv.](../media/5-3-transform.png)](../media/5-3-transform.png#lightbox)

1. Select the **Transform Data** button. This will launch the Power Query Editor window.

    > [!NOTE]
    > When you're working in Power Query, it's best to maximize the Power Query Editor window so you can see a full view of the Power Query window menus, panes, and options.

1. By default, the **Queries** pane on the left side of the Power Query Editor window will be collapsed. Select the **arrow** in the Queries pane to expand and open the Queries pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor window with the Queries pane collapsed and the arrow shown to expand the pane.](../media/5-4-expand-pane.png)](../media/5-4-expand-pane.png#lightbox)

1. In the **Queries** pane, right-click the default query name called **MAIAD Lab 01 - Data Source - Customers** and then **Rename** the query to **Customers**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Queries pane open, showing Lab 01 - Data Source - Customers query and the Rename button highlighted.](../media/5-5-rename.png)](../media/5-5-rename.png#lightbox)

    > [!TIP]
    > Queries that you use as part of a Data Model should be given a clear, descriptive, user-friendly, noun name that describes what the data represents. For example, Customers, Quotes, Invoices, Products, Geography, and so on.

## Exercise 2: Use Power Query transformations to Split Column by Delimiter - Customers

In this exercise, you'll use Power Query to extract the First Name from the Contact column.

### Task 1: Use Column from Example

In this task, you'll create a new column called **First Name** by using the **Add Column > Column from Examples** transformation to split the **Contact** by a delimiter.

1. From the **Preview** grid, select the **Contact** column.

1. From the **Add Column** Tab, select the **Column from Examples** down arrow, then select the **From Selection** option.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Power Query Editor window displaying the Add Column menu options.](../media/5-6-add-column.png)](../media/5-6-add-column.png#lightbox)

    > [!NOTE]
    > This opens a *new* user interface window called "Add Columns From Examples." This window looks like the Power Query Preview grid, but it is separate window allowing you to type in the proposed value so that Power Query can identify the pattern and formula to apply achieving the end results.

1. In the **Add Column From Examples** window, in the column called **[Column1]**, type the value **"Hugo"** and then enter.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Add Column From Examples window showing Hugo entered in Column1.](../media/5-7-add-from-examples.png)](../media/5-7-add-from-examples.png#lightbox)

    > [!NOTE]
    > After you press the **Enter** key, Power Query will identify if a pattern exists in the data to populate the values for all rows.

1. **Double-click** in the default header called **"Text Before Delimiter"** and rename the new column as **"First Name"**. Select the **OK** button.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Column From Examples window showing the renaming of the default column name to First Name.](../media/5-8-rename.png)](../media/5-8-rename.png#lightbox)

    > [!NOTE]
    > Now, in the Power Query Editor preview grid, you'll notice the NEW column called *First Name*, created by parsing out the [First Name] from the [Contact] using the Column from Example transformation.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Preview grid in Power Query Editor showing the new First Name column.](../media/5-9-first-name.png)](../media/5-9-first-name.png#lightbox)

## Exercise 3: Use Power Query to connect to XLSX - Quotes.xlsx

In this exercise, you'll use Excel to connect to an XLSX source data file.

### Task 1: Connect to XLSX source data from within the Power Query Editor window

In this task, you will start from within the **Power Query Editor** window.

1. From the Power Query **Home** menu, select the **New Source > Excel Workbook** file option.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor window showing the Home tab options with the New Source > File > Excel Workbook option selected.](../media/5-10-new-source.png)](../media/5-10-new-source.png#lightbox)

1. Navigate to the file **C:\ANALYST-LABS\Lab 01\Data Source - Quotes.xlsx**.

1. In the Navigator window, select the worksheet called **"Lab 01 - Quotes"**.

    > [!NOTE]
    > This is *only* a preview of the data.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Navigator window showing the Lab 01A - Quotes worksheet highlighted.](../media/5-11-navigator.png)](../media/5-11-navigator.png#lightbox)

1. Select the **OK** button to load as a second query in the Power Query Editor window.

1. In the **Queries** pane, right-click on the default query name called "Lab 01 - Quotes" to **Rename** the Query to "Quotes."

    > [!div class="mx-imgBorder"]
    > [![Screesnshot of the Queries pane in the Power Query Editor window, with the Lab 01 - Quotes name selected for renaming.](../media/5-12-rename.png)](../media/5-12-rename.png#lightbox)

## Exercise 4: Use Power Query to Unpivot - Quotes

In this exercise, you'll use Power Query transformations to structure the Quotes data for Power Pivot.

### Task 1: Use First Row as Headers transformation button

In this task, you'll move the first row with the column header values to the table header.

On the **Home** menu, select the **Use First Row as Headers** button.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Home tab showing the Use First Row as Headers button selected.](../media/5-13-use-first-row.png)](../media/5-13-use-first-row.png#lightbox)

### Task 2: Use the Unpivot transformation menu option

In this task, you'll unpivot the Quotes data.

1. In the **Preview** pane, right-click the **CustID** column to display menu options.

1. Then choose the **Unpivot Other Columns** option.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the CustID column and the Unpivot Other Columns option highlighted for selection.](../media/5-14-unpivot.png)](../media/5-14-unpivot.png#lightbox)

1. Double-click the **Attribute** column, then rename it **QuoteDate**.

1. Double-click the **Value** column, then rename it **QuoteAmt**.

    *Before*

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the CustID, Attribute, and Values column headers before they're renamed.](../media/5-15-before.png)](../media/5-15-before.png#lightbox)

    *After*

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Attribute and Value columns renamed to QuoteDate and QuoteAmt.](../media/5-16-after.png)](../media/5-16-after.png#lightbox)

## Exercise 5: Use Power Query to Clean - Quotes

In this exercise, you'll use Power Query transformations to clean the Quotes data.

### Task 1: Use the Replace transformation

In this task, you'll use a replace technique to change the QuoteDate to a full date that you can convert to a Date data type.

1. In the Preview window, right-click the **QuoteDate** column to display menu options.

1. Next, choose the **Replace Values...** option.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the QuoteDate column highlighting the Replace Values menu option.](../media/5-17-replace.png)](../media/5-17-replace.png#lightbox)

1. In the **Replace Values** UI window:

    1. Enter a hyphen **-** in the **Value To Find** text box.

    1. Enter **/1/** in the **Replace With** text box.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Replace Values window showing entries in the Value To Find and the Replace With text boxes.](../media/5-18-replace-values.png)](../media/5-18-replace-values.png#lightbox)

    1. Select the **OK** button.

### Task 2: Use the Data Type icon

In this task, you'll use the Data Type icon to change the data type from Text to Date.

1. Select the **ABC** icon in the **QuoteDate** column header that indicates the column is a Text data type.

1. Choose the **Date** option from the data type menu options.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the QuoteDate data format icon selected.](../media/5-19-data-type.png)](../media/5-19-data-type.png#lightbox)

### Task 3: Close and load to the data model

In this task, you'll load the Customers and Quotes tables to the data model.

1. From the **Home** menu, select **Close & Load > Close & Load To...**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Close & Load button selected and the Close & Load To option highlighted.](../media/5-20-close-load-to.png)](../media/5-20-close-load-to.png#lightbox)

1. On the Import window, select the **Only Create Connection** radio button.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Import Data window displaying the Only Create Connection button and the Add this data to the Data Model checkbox selected.](../media/5-21-only-connection.png)](../media/5-21-only-connection.png#lightbox)

1. Check the box next to **Add this data to the Data Model**.

1. Select the **OK** button.

    > [!NOTE]
    > The loaded Tables are displayed in the Queries & Connections Pane window with total number of rows loaded.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Queries & Connections pane displaying the Customers query with 7,560 rows loaded and the Quotes query with 84,307 rows loaded.](../media/5-22-queries.png)](../media/5-22-queries.png#lightbox)

    > [!NOTE]
    > At this point, we've connected to the data sources using Power Query and selected the checkbox option to **Add this data to the Data Model**. However, we haven't actually seen where this data has been loaded. In Lab 02A, we'll use Power BI Desktop to Import the Power Query connections, Customer table, and Quote table to create the Data Model.

    > [!NOTE]
    > To edit the Queries and re-launch the Power Query Editor window, Select **Data** > **Queries & Connections** to display the Queries & Connections pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Queries & Connections button under Data tab.](../media/lab-queries-and-connections-pane.png)](../media/lab-queries-and-connections-pane.png#lightbox)

    > [!NOTE]
    > When you select **Close and Load To…** and set the Import Data options for the first time, this is the default setting.  You can always edit these settings by right-clicking the **Query** in the Queries & Connections Pane, then selecting the **Load To…** option to display and update the Import Data settings.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Load To... option in the context dialog for an item in the Queries & Connections pane.](../media/lab-load-to.png)](../media/lab-load-to.png#lightbox)

### Task 4: Save the file

In this task, you'll save the Excel file with the **Customers** and **Quotes** query connections.

1. From the main Excel ribbon, select **File > Save**.

1. Go to the **C:\ANALYST-LABS\Lab 01** folder and then save the file as **Lab 01 - My Solution.xlsx**.

### Summary

In this lab, you used Power Query in Excel to connect to CSV and XLSX source data files, created a new column using Column from Example, unpivoted and applied transformations in Power Query, loaded source data to a Data Model, and saved the Excel file with the data connections.

> [!div class="mx-imgBorder"]
> [![Screenshot of the final results in Excel showing the Customers and Quotes queries.](../media/5-23-final.png)](../media/5-23-final.png#lightbox)
