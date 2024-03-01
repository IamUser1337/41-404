## Open an Excel file and create an instance

The first task in automating any Excel-related task is to create an Excel instance.

An instance determines which application session Power Automate for desktop will interact with. Create instances by opening a locally stored or new Excel file or by attaching the flow to an already opened file. These operations are achieved by the **Launch Excel** action or the **Attach to running Excel** action.

To open a new Excel file, under **Launch Excel**, select **with a blank document**.

![Screenshot of Launch Excel action properties dialog.](..\media\launch-excel-action-properties.png)

Alternatively, launch Excel with an existing file by changing the **Launch Excel** setting to **and open the following document**. Enter a **Document path**, or browse for and select a file.

To view the Excel actions when the flow runs in real time, check the **Make instance visible** check box. The Excel window opens when the flow runs. If the checkbox isn't checked, Excel runs in the background. Expand the **Advanced** section, which includes an option to **Load add-ins and macros** as the Excel file launches.

Use an already opened Excel file as an instance with the **Attach to running Excel** action. With this action, specify the **Document name**.

![Screenshot of Attach to running Excel action properties dialog.](..\media\attach-to-running-excel-action-properties.png)

## Save and close an Excel file

You can save and close an Excel file only if the instance has already been determined. To save an Excel file,  use the **Save Excel** action.

To save the document in its current path with its current filename, set the **Save mode** option to **Save document**. To save the document in a different path and/or under a different file name set the option to **Save document as**.

![Screenshot of Save Excel action properties dialog.](..\media\save-excel-action-properties.png)

Select **Save document as**, to show additional options to change the **Document format** and to provide the new **Document path**.

![Screenshot of Save Excel action properties dialog with Save mode set to Save document as, and Document format and Document path highlighted.](..\media\save-excel-action-properties-continued.png)

Close a specific instance of Excel with the **Close Excel** action. Optionally, save the file with any of the **Before closing Excel** options.

Use any of the options to save the document, and the action will function similarly to the **Save Excel** action, in addition to closing the document.

![Screenshot of Close Excel action properties dialog.](..\media\close-excel-action-properties.png)
