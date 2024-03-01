The SharePoint connector in Microsoft Power Automate comes with a **Send an HTTP request to SharePoint** action.

> [!div class="mx-imgBorder"]
> [![Screenshot of SharePoint action to send an HTTP request to SharePoint.](../media/image-1.png)](../media/image-1.png#lightbox)

The following sections will describe how to use the **GET**, **POST**, and **DELETE** methods to change a list in Microsoft Lists.

> [!div class="mx-imgBorder"]
> [![Screenshot of available methods to change a list in Microsoft Lists.](../media/image-2.png)](../media/image-2.png#lightbox)

## Use the GET method to get an item from SharePoint

The GET method allows you to use the REST API of SharePoint to find specific information. In this example, you can confirm if the **location** list name exists in SharePoint.

The **Manually trigger a flow** action triggers a flow without input. The **Send an HTTP request to SharePoint** action is the main action to gather the information that you seek.

**Site Address**, **Method**, **Uri**, and **Headers** are the required fields.

This example shows that you are able to **GET** the information of a specific item.

> [!div class="mx-imgBorder"]
> [![Screenshot of the GET method with item information.](../media/image-3.png)](../media/image-3.png#lightbox)

When the flow runs successfully, it confirms that the list exists and provides information in return.

> [!div class="mx-imgBorder"]
> [![Screenshot of the successful flow with details returned.](../media/image-4.png)](../media/image-4.png#lightbox)

## Use the POST method to add and edit an item

To add an item to a list, you need an action with the following settings:

- **Site Address** - `https://domainame.sharepoint.com/sites/sitename`

- **Method** - POST

- **Uri** - /_api/web/lists/getbytitle('*listname*')/items

- **Headers** - Accept and Content-Type

The following screenshot shows what the action looks like.

> [!div class="mx-imgBorder"]
> [![Screenshot example of the action with details highlighted.](../media/image-5.png)](../media/image-5.png#lightbox)

The following screenshot shows an example of a successful run.

> [!div class="mx-imgBorder"]
> [![Screenshot of the successful run details.](../media/image-6.png)](../media/image-6.png#lightbox)

Editing requires you to provide the exact item number and other headers.

Consider a list that contains the items that are shown in the following image.

> [!div class="mx-imgBorder"]
> [![Screenshot example of a list of items.](../media/image-7.png)](../media/image-7.png#lightbox)

By using the following **HTTP request to SharePoint** action, change the **Test 3** title of item 3 to **New Test 3**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the HTTP request to SharePoint action.](../media/image-8.png)](../media/image-8.png#lightbox)

After the flow has run successfully, the list item will be updated.

> [!div class="mx-imgBorder"]
> [![Screenshot of the list item updated after the successful flow.](../media/image-9.png)](../media/image-9.png#lightbox)

## Use the DELETE method to delete an item

The DELETE method is similar to the EDIT method, except that you will be updating the **X-HTTP-Method** from **MERGE** to **DELETE**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the delete method details.](../media/image-10.png)](../media/image-10.png#lightbox)

After the flow has run successfully, the list item will be deleted.

> [!div class="mx-imgBorder"]
> [![Screenshot of the item deleted after the successful flow.](../media/image-11.png)](../media/image-11.png#lightbox)
