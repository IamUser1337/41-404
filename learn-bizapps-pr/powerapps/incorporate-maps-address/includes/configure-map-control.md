The map control is a premium control that takes full advantage of the native geospatial capabilities within Power Apps. It contains many properties that allow you to zoom, tilt, navigate, rotate, and interact with a map in an all-in-one experience. You can input data to your map, show pins, routes and waypoints from various data sources. It's able to display various map styles, such as road, satellite, and high contrast options.

> [!div class="mx-imgBorder"]
> [![Screenshot of the map control for a canvas app.](../media/map-control.png)](../media/map-control.png#lightbox)

This control can receive input from other controls in your app, such as the **Address input** control, but it renders a location according to any latitude and longitude data. It can also receive input data via an API, though we don't cover the API technique in this unit (look for a link in the Summary).

After adding the map control to the canvas app, you'll have access to many properties that you can interact with through the **Properties** menu or through **Power *fx*** formulas. In this lesson, you'll learn about several of these properties and their setup.

The following screenshot is an example map control that has been added to a canvas app showing the **Properties** panel on the right with some of the available configuration options.

> [!div class="mx-imgBorder"]
> [![Screenshot of the interactive map control and the fields that are available to use.](../media/map-control-properties.png)](../media/map-control-properties.png#lightbox)

When you enable the **Use default location** feature, the map automatically starts at a certain location when it first loads, providing a consistent user experience. When enabled, the map always renders at the location that's specified in the default latitude and longitude fields with the default zoom level.

> [!div class="mx-imgBorder"]
> [![Screenshot of the default location properties of the interactive map for an app.](../media/default-location-properties.png)](../media/default-location-properties.png#lightbox)

The map can automatically show the user's current location on the interactive map when you set the **CurrentLocation** field to **true** and use the **Location.Latitude** and **Location.Longitude** settings in the respective **CurrentLocationLatitude** and **CurrentLocationLongitude** properties.

To enable this feature, you must turn on the **Show current location** and disable the **Use default location**

> [!div class="mx-imgBorder"]
> [![Screenshot of the current location properties of the interactive map for an app.](../media/current-location-properties.png)](../media/current-location-properties.png#lightbox)

Depending on the application's requirements, or where you use it, the map control can display the picture in different views. For instance, you can use a satellite view to see the actual buildings and roads as they appear either with or without street and building information applied. Alternatively, the map can show a digitally rendered version in dark or light modes with three different types of roads. Some views might be better for navigation while others might be more optimal for accessibility or research purposes.

> [!div class="mx-imgBorder"]
> [![Screenshot of the different styles for an interactive map and how they appear in the application.](../media/map-styles.png)](../media/map-styles.png#lightbox)

The map control also has embedded controls, such as **Zoom**, **Compass**, and **Pitch**, that you can enable so that users of the canvas app can view the location from different perspectives.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Zoom, Compass, and Pitch controls for an interactive map and how each can change the appearance of the map.](../media/map-zoom-compass-pitch.png)](../media/map-zoom-compass-pitch.png#lightbox)

You can assign data sources to the maps via the **Items** property. A data source containing coordinates allows you to insert pins on the map. You can use this feature for business-use cases such as delivery locations, customer locations, and more.

When you select icons for the different pins in a data source, you can select from any Microsoft Azure pins.

> [!div class="mx-imgBorder"]
> [![Screenshot of the data source selection for a map control.](../media/map-data-source.png)](../media/map-data-source.png#lightbox)

For pins that are placed on a map, you can view associated information for that pin to provide canvas-specific information. To do so, point to the pins or select them, depending on the configuration in the **Show info cards** and the fields that are selected to display. You can set the color of the pins for the entire control in the properties or from the data source for each individual pin.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Cluster pins, Show info cards, and Pin color configurations for an interactive map.](../media/cluster-information-cards.png)](../media/cluster-information-cards.png#lightbox)

If multiple pins are located closely together, you can use the **Cluster pins** configuration to group all pins together until users adjust their zoom to have a better view of those pins.

> [!div class="mx-imgBorder"]
> [![Screenshot example of the Cluster pins feature on a map control.](../media/cluster-pins.png)](../media/cluster-pins.png#lightbox)

In the next unit, we'll show you a demonstration of how this control can interact with other controls.
