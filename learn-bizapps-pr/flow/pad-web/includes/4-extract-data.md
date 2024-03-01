Apart from handling web forms and components, Power Automate for desktop enables you to extract data and details from web pages.

To extract information about a web page, use the **Get details of web page** action.  Through this action, you can retrieve descriptive details about web pages, such as its title, metadata keywords, and description. In the action's properties, you have to specify the browser instance and the desired information to retrieve.

![Screenshot of the Get details of web page action.](..\media\get-details-of-web-page-action.png)

To extract details about a specific element rather than the entire web page, you can use the **Get details of element on web page** action. This action requires a browser instance and a UI element describing the element.

![Screenshot of the Get details of element on web page action.](..\media\get-details-of-element-on-web-page-action.png)

If you want to take a screenshot from a web page, you can use the **Take screenshot of web page** action. Deploying this action, you can take a screenshot of the entire web page or a specific element. The action allows you to store the taken screenshot to the clipboard or a file.

![Screenshot of the Take screenshot of web page action.](..\media\take-screenshot-of-web-page-action.png)

## Advanced data extraction

It's common in business procedures to extract web data displayed in the form of tables and lists. Power Automate for desktop enables you to automate these procedures through the **Extract data from web page** action.

Like the other web actions, the **Extract data from web page** action requires a browser instance containing the page from which you'll extract data.

![Screenshot of the Extract data from web page action.](..\media\extract-data-from-web-page-action.png)

You can save the extracted data into a variable or a newly generated Microsoft Excel spreadsheet. Depending on the selection, the extracted data can be in any of the following forms:

- **Single value** - The value is stored as a text. The action uses this data form to extract a single value, like a product's name.

- **Handpicked (multiple) values** - The values are stored in a list. The action uses this data form to extract multiple values, like the name and price of a product.

- **Lists** - The action uses this data form to extract a single value from multiple registries, like all available product names.

- **Tables** - The action uses this data form to extract multiple values from multiple registries, like all available product names and prices.

To specify which data to extract, you have to launch a browser window while the **Extract data from web page** is open and wait for the **Live web helper** dialog to appear.

While the platform displays the **Live web helper** dialog, right-click on the desired element, select **Extract element value**, and choose the property you want to extract.

![Screenshot of an extracted single value.](..\media\extract-single-value.png)


To extract data spread throughout multiple pages, right-click on the website's pager button and select **Set element as pager**.

If you want to modify the CSS selectors manually, select the **Advanced settings** option. Manually selector editing allows you to create complex selectors when the automatic selection doesn't satisfy your needs.

![Screenshot of the advanced settings of the Live web helper.](..\media\web-helper-advanced-settings.png)

To discard a selection you have made, select the **Reset** button on the **Live web helper** dialog.

Lastly, you have both the **Pause** and the **Reset** button options available. The pause will stop the recording to occur and reset will clear all the existing recordings. You can clear individual actions by clicking on the trash icon next to it.

![Screenshot of the Live web helper dialog.](..\media\web-helper-dialog.png)
