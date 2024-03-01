# Retail story

Contoso Retail wants to provide its users with a customized experience of Store Operations Assist by updating their company logo on the app and providing coloring that's specific to forms. Also, they plan to change the default theme of the application for the users. 

You can personalize the Store Operations Assist solutions by creating a custom appearance and behavior. You can change the default colors and visual elements that are provided in the default theme of the application. Additionally, you can set up the theme colors and apply them globally throughout the application. Store Operations Assist supports themes that the Dynamics 365 platform provides.

## Personas and scenario 

In this exercise, you assume the role of Oscar and perform the following tasks:

- Customize the theme for the Store Operations Assist Admin.

- Change the default background color for Store Operations Assist Mobile.

- Enable push notifications for Store Operations Assist Mobile.

## Task: Customize the theme for Store Operations Assist Admin

In this task, you act as Oscar and change the logo and theme of Store Operations Assist Admin.

1. Go to [Microsoft Power Apps](https://make.powerapps.com/?azure-portal=true) in an Incognito or InPrivate browsing session. Ensure that you're in the correct environment.

1. On the left navigation pane, select **Apps**. Select the play button that appears near Store Operations Assist.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps with play button highlighted near Store Operations Assist.](../media/play-soa-app.png)](../media/play-soa-app.png#lightbox)

1. Select **Settings > Advanced Settings**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Store Operations Assist with the Settings dropdown menu selected to reveal Advanced Settings.](../media/advanced.png)](../media/advanced.png#lightbox)

1. Select **Settings > Customizations**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Settings with focus on Customizations.](../media/customization.png)](../media/customization.png#lightbox)

1. Select **Themes** in the **Customization** area.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Customization screen showing the Themes option selected as the feature to work with.](../media/themes.png)](../media/themes.png#lightbox)

1. Select **New** to create a new theme.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the All Themes screen with focus on the New button.](../media/new-theme.png)](../media/new-theme.png#lightbox)

1. On the **New Theme** form, enter these details:

   - **Theme Name** - Enter **Contoso Retail Theme**.

   - **Logo** - Select **New resource** to upload and assign a new logo for Contoso Retail. 
                [Download the Contoso logo.](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/retail-cloud/Contosologo.jpg)

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the logo to use for Contoso Retail.](../media/contoso-logo.jpg)](../media/contoso-logo.jpg#lightbox)

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the New Theme form in Dynamics 365, showing the Logo field expanded to show 10 results with focus on the New button.](../media/new-web-resource.png)](../media/new-web-resource.png#lightbox)

1. In the new resource form, enter these details:

   - **Name** - new_ContosoLogo

   - **Display Name** - Contoso Retail Logo

   - **Description** - Contoso Retail's Logo

   - **Type** - JPG format

   - **Language** - English

   - **Upload file** - Upload the JPG file that's provided in the previous step

   - **Mobile** - Select **Enable for mobile**

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Web Resource: New page in Power Apps with focus on the Choose File button.](../media/choose-file.png)](../media/choose-file.png#lightbox)

1. After entering the details, select **Save**.

1. Select **Publish** to publish the logo for use.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Web Resource: Contoso Retail logo page in Power Apps with focus on the Publish button.](../media/publish.png)](../media/publish.png#lightbox)

1. In the **Themes** form, for **the Contoso Retail** theme, look up the **logo** field and then select the **new_ContosoLogo** resource.

1. Search for **new_ContosoLogo** and then select **Add**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Lookup Record dialog, showing search results for new contoso.](../media/new-contoso.png)](../media/new-contoso.png#lightbox)

1. Update the **Default Entity Color** field to **001CA5**. (The default color is grey. It's updated to blue.)

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the New Theme form with focus on the Default Entity Color entry.](../media/entity-color.png)](../media/entity-color.png#lightbox)

1. Select **Save** and then select **Publish** to make the theme the **Default** theme.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Dynamics 365 Settings with focus on the Publish Theme button.](../media/publish-theme.png)](../media/publish-theme.png#lightbox)

1. Go to the home page to view the updated logo and color theme.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Store Operations Assist with the updated logo.](../media/updated.png)](../media/updated.png#lightbox)

## Task: Change the default background color for Store Operations Assist Mobile

In this task, you act as Oscar and change the default background color of Store Operations Assist Mobile:

1. Go to [Power Apps dashboard](https://make.powerapps.com/).

1. Select your Store Operations Assist environment in the upper right.

1. Select **Solutions** in the left pane and under **Unmanaged** tab, select **Default Solution**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps Solutions showing the Default Solution.](../media/default-solution-selected.png)](../media/default-solution-selected.png#lightbox)

1. Go to **Setting definitions** in the left navigation pane, search for and select the **MobileBackgroundColor** setting, and then select **Edit**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps on the Setting definitions page.](../media/setting-definitions.png)](../media/setting-definitions.png#lightbox)

1. On the right pane, under the **Setting environment value** area, select **New environment value**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Setting definitions page in Power Apps with Edit Mobile Background expanded and focus on the New environment value option.](../media/environment-value.png)](../media/environment-value.png#lightbox)

1. Enter the hex color that you want the background to be (such as **CEEAFF**), and then select **Save** to override the default value.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the hex value entered to override the default.](../media/hex-value.png)](../media/hex-value.png#lightbox)

1. After the mobile background color has been updated, publish the changes by selecting **Publish all customizations**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps with focus on the Publish all customizations option.](../media/publish-customizations.png)](../media/publish-customizations.png#lightbox)

1. Go to Store Operations Assist Mobile, which shows that the background color is updated.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the mobile app showing the new background color.](../media/mobile-app.png)](../media/mobile-app.png#lightbox)

   > [!NOTE]
   > Currently, no scope is available for changing font text colors in Store Operations Assist Mobile.

## Task: Set up push notifications

Store Operations Assist offers push notifications capability in Store Operations Assist Admin and Store Operations Assist Mobile. You can use push notifications to send updates to store associates through their devices. Push notifications use Microsoft Power Automate and they're triggered by many scenarios, such as task assignment, task review, and so on. Contoso Retail uses the push notifications feature to keep store associates updated with the latest task assignment and completion.

### Prerequisites

Make sure that you meet the following prerequisites before starting this exercise:

- A Microsoft Power Automate license

- Consent for notifications in your device's settings (allow notifications in device settings)

In this exercise, you act as Oscar, the IT administrator for Contoso Retail, to enable push notifications:

1. Go to [Power Apps](https://make.powerapps.com/?azure-portal=true). In the upper-right corner, select the Store Operations Assist environment that you created in the prerequisites.

1. Select **Solutions** in the left pane. Go to **Default Solution** and select **Edit**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps with Default Solution selected.](../media/default-solution-selected.png)](../media/default-solution-selected.png#lightbox)

1. In **Connection references**, edit the **Power Apps Notification V2** connection.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Connection references with focus on the Power Apps Notification V 2 connector.](../media/notification.png)](../media/notification.png#lightbox)

1. On the edit screen, select **New connection** under **Connection**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Edit Power Apps Notifications with focus on the New connection option.](../media/connection-new.png)](../media/connection-new.png#lightbox)

1. On the **New connection** screen, search for and select **Power Apps Notification V2**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of New connection with focus on Power Apps Notification V 2.](../media/power-apps-notification.png)](../media/power-apps-notification.png#lightbox)

1. Select **Create** to create a connection for **Power Apps Notification V2**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps Notification V 2 pop-up window, showing the Create button.](../media/create-notification.png)](../media/create-notification.png#lightbox)

1. Select the new connection that you created for **Power Apps Notification V2** on the **Edit connection reference** screen and then select **Save**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Edit Power Apps Notification dialog showing the Connection field filled in.](../media/save-connection.png)](../media/save-connection.png#lightbox)

1. Similarly, edit the **Microsoft Dataverse msret_RetailConnectUI-576c7** connection and then select **New connection**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Edit Microsoft Dataverse.](../media/dataverse.png)](../media/dataverse.png#lightbox)

1. Create a **Microsoft Dataverse** connection by using the administrator credentials that you're using for this exercise.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of New connection with focus on Microsoft Dataverse.](../media/create-dataverse.png)](../media/create-dataverse.png#lightbox)

1. Save the connection reference.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the saved connection.](../media/saved.png)](../media/saved.png#lightbox)

1. In the **Cloud flows** section, ensure that the following flows are turned on. If not, select **Turn on** from the ribbon to start the flows.

   - When a Request Row is added or modified

   - When a task row is added, modified

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Cloud flows with focus on the two flows.](../media/when-modified.png)](../media/when-modified.png#lightbox)

