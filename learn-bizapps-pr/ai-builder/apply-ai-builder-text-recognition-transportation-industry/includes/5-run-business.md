## Check work

To check that what you have created so far is working and can be released, we must fake a real world scenario and ensure that the entire flow can be achieved.

Linda receives a transport request from Fabrikam, Inc for container to be shipped from San Francisco to Delhi. She opens the "Contoso Container Tracking" application and uses the "New button".

She enters all the information using the data entry form and saves.

![New Container Shipment form on the General tab filled in with a Save button at the top.](../media/image14.png)

She can now see this new container, which is waiting to be shipped.

![The new container appears in the Containers List.](../media/image15.png)

John, the docker worker from San Francisco, has managed to carry the container on a boat and uses the "Contoso Container Check-in" application to update the status. He takes a picture of the container, selects the text with the container identifier, and updates the shipment date.

>[!NOTE]
>AI Builder text recognizer also supports uploading a picture from local device.

![Container Check-in and Update shipping screens appear side by side.](../media/image16.PNG)

Linda can now see that the container is on his way to Delhi in "Contoso Container Tracking" application.

![Container tracking application shows the shipment with a Delivery State of In Transit.](../media/image17.png)

After 20 days of travel, Chanda, the docker worker from Delhi, receives and unloads the container from the boat. She uses the "Contoso Container Check-in" application to update the status. She takes a picture of the container, selects the text with the container identifier, and updates the arrival date.

![Update shipping screen shows the Arrival Date updated.](../media/image18.png)

Linda can now see that the container has been delivered to Delhi and can inform her customer.

![Container tracking application shows the shipment with a Delivery State of Delivered.](../media/image19.png)

## Summary

You've now successfully tested that your business scenario is working end to end. You're now ready to release these applications to your users improving the way your company will run his business thanks to the magic of AI and Microsoft Power Platform!
