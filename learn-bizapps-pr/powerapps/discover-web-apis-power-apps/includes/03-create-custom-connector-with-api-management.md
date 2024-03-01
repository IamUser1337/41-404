In this exercise you're going to create a custom connector by exporting an API from Azure API Management.

In the VanArsdel fusion development scenario, Maria needs to display warehouse locations in her Power Apps application. Kiana and her development team have built several web APIs one of which returns the warehouse locations.

The web APIs are served through [Azure API Management][az apim], which has the ability to create custom connectors for any web APIs it hosts. With the custom connector, Maria's Power Apps app will be able to call the warehouse location API in Azure API Management.

> [!NOTE]
> If you want to use Azure API Management and Power Apps throughout the exercises in this module you will need to follow a couple of steps.
> 
> The first is to [download the web API files from GitHub][artifacts], unzip the archive, and provision and deploy them to API Management using the instructions included in the README file.
> 
> The second is Power Apps requires either a Microsoft 365 license or a free trial. Learn more about your licensing options. [Microsoft products include Microsoft Power Apps and Power Automate][pa pricing].


## Export a web API from API Management to a custom connector ##

1. You need a subscription key in order for Power Apps to access any web API hosted in API Management. Go to the `Subscriptions` blade, click the three dots (`...`) and select the `Show/hide keys` menu.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-01.png" alt-text="Subscription Blade":::

1. Then, copy the subscription key from either `Primary key` or `Secondary key`.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-02.png" alt-text="Copy Subscription Key":::

1. To generate a custom connector from Azure API Management, go to the `APIs` blade and select an appropriate API under the `All APIs` section. In the screenshot, it's **Inventory Management**. Then, you will be able to see the API for the warehouse locations.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-03.png" alt-text="Inventory Management APIs on API Management":::

1. Click the three dots (`...`), and you will see the context menu. Select the `Export ⬇️` menu.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-04.png" alt-text="API Export Menu on API Management":::

1. Click the `Power Apps and Power Automate` panel at the right bottom corner.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-05.png" alt-text="API Export Screen on API Management":::

1. Choose your Power Apps environment for the custom connector to publish and give the display name, **InventoryManager**. Then click the `Export` button at the bottom.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-06.png" alt-text="Export API to Power Apps":::

The inventory management APIs have been exported to Power Apps.


## Create a connection to the custom connector ##

You need to create a connection to the custom connector in order to use it. Generally speaking, creating the connection requires authentication to the web APIs.

1. After logging into [Power Apps][pa] dashboard, open the `Data` blade and click the `Custom Connectors` menu on the left-hand side. Then, click the `➕` button on the right-hand side.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-07.png" alt-text="New Custom Connector":::

1. When a pop-up modal shows up, you will see the API Key field enabled. Enter the API key copied at the beginning of this unit. Then click the `Create` button.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-13.png" alt-text="New Custom Connector Pop-up Modal":::

1. Go to the `Connections` menu, and you will see the new connection has been created.

    :::image type="content" source="../media/03-create-custom-connector-with-api-management-14.png" alt-text="New Connection":::

You have completed creating a custom connector for inventory management.

[az apim]: /azure/api-management/api-management-key-concepts
[az cli install]: /cli/azure/install-azure-cli
[pa]: https://powerapps.microsoft.com/
[pa cp]: https://powerapps.microsoft.com/communityplan/?azure-portal=true
[pa pricing]: /power-apps/administrator/pricing-billing-skus/?azure-portal=true

[artifacts]: https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/fusion-developers/artifacts.zip
