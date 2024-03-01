You've created the connector, tested it, and now you'll learn how to use it in a canvas app.

> [!NOTE]
> Power Apps requires either an Microsoft 365 license or a free trial. Learn more about your licensing options. [Microsoft products include Microsoft Power Apps and Power Automate][pa pricing].


## Create a canvas app ##

1. First of all, create a blank canvas app. In Power Apps studio go to the `Create` menu at the left-hand side and click the `Canvas app from blank` panel.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-01.png" alt-text="Create Power Apps":::

1. When a modal pops up, give the name, **Inventory**, to the `App name` field and leave the format as default. Then click the `Create` button.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-02.png" alt-text="Create Power Apps Modal":::

1. Navigate the `Data` menu to add the custom connector. You will see nothing in the Data pane.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-03.png" alt-text="Data Pane":::

1. Click the `Add data` button and enter **inventory** in the search box, and you will see the `InventoryManager` custom connector. *(Assuming you named your custom connector `InventoryManager`.)*

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-04.png" alt-text="Custom Connector Search":::

1. Click the `InventoryManager` connector, and you will see the `InventoryManagement` connection.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-05.png" alt-text="Connection Added":::

1. Your custom connector is successfully added to your Power Apps. Navigate to the `Insert` menu at the top and click `Button` to add a button control onto the canvas.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-06.png" alt-text="Add Button":::

1. While `Button1` is selected, choose the property value to **OnSelect** and enter the function formula below. `InventoryManagement` represents the custom connector and `getapiwarehouselocations()` represents an API endpoint. The `warehouses` collection stores the result that the `getapiwarehouselocations()` function returns.

    ```powerappsfl
    ClearCollect(warehouses, InventoryManagement.getapiwarehouselocations())
    ```

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-07.png" alt-text="Add Formula":::

1. Click `Gallery` and select the `Vertical` control.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-08.png" alt-text="Add Vertical Gallery":::

1. Once the `Vertical` control is added, it asks the data source.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-09.png" alt-text="Vertical Gallery  Added":::

1. Select the `warehouses` collection declared above. Then the `Vertical` control changes below because the `warehouses` collection currently contains nothing.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-10.png" alt-text="Vertical Gallery Data Source Mapped":::

1. While holding your `Alt` key on Windows (or `Option` key on Mac), click the `Button` button, and you will see the list of warehouse locations showing up in the `Vertical` control.

    :::image type="content" source="../media/08-use-custom-connector-in-power-apps-11.png" alt-text="Custom Connector Result in Vertical Gallery":::

You have successfully included the custom connector into your Power Apps app.


[pa pricing]: /power-apps/administrator/pricing-billing-skus/?azure-portal=true
