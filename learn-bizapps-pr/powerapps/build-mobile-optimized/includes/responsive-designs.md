In this exercise, we create a mobile-optimized one-screen app based on our Contoso Coffee Machines data. The purpose of this exercise is to give you experience building an app with auto-layout containers, and to show you first-hand how responsive apps behave. We create a brand-new app, so head to the Power Apps home page and follow these steps.

1. Download the Excel spreadsheet [CoffeeMachineData.xlsx](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-apps/coffee-machine-data/CoffeeMachineData.xlsx). Select the link and then the **Download raw file** button to download the file. Once it downloads, continue with the next step.

1. Select **Create** > **Blank app** > **Tablet**. Provide your app with a name and press **Create.**

1. In the command bar, select the **Settings** button. (You might need to select **App** in the **Tree view** panel to show it.)

1. In the **Settings** popup panel, select the **Display** tab, then scroll down and turn **Off** the **Scale to fit** option (this action automatically switches the **Lock aspect ratio** to **Off**).

1. Close the **Settings** popup.

1. Create a **New screen** with a **Sidebar** layout for your app. Name it "Catalog Screen."

1. Create a **New screen** from the **Templates** > **Success**.

1. Delete **Screen1**.

1. Next select the **Add data** button from the command bar. Then find/select **OneDrive for Business**.

1. Under the **Choose an Excel file** panel on the right side of your screen, select your **CoffeeMachineData.xlsx** file, then select the **CoffeeMachines** table. Connect the table by selecting **Connect** at the bottom of the panel.

1. Select the horizontal container on the left side of your screen, called **SidebarContainer1**.

1. Select the plus (**+**) icon in the container and insert a **Vertical gallery** into **SidebarContainer1** and select **CoffeeMachines** as the data source. Set the **Fill** property to Color.LightSteelBlue.

1. Select **Form1** and the plus **(+)** icon to insert an **Edit form**. In the **Properties** panel on the right side of the screen, select **CoffeeMachines** as the **Data source**.

1. Still in the Properties panel, select the Edit fields option under the Data source.

1. In the **Fields** panel, select **Add field** and add all the fields by checking the box next to each field name in the Choose a field popup. Then select the **Add** button at the bottom.

1. Close the **Fields** panel.

1. While the **Form1** is still selected, in the **Property** dropdown menu at the top left of the screen, select the **Item** property, and in the formula (***fx***) field input: Gallery1.Selected

1. Finally, still on your form, set the **Fill** property to: Color.LightSteelBlue

1. Next, we add to our header container. Select the **HeaderContainer** control and use the plus (**+**) icon to insert a **Text label** control, and adjust the properties in the dropdown as follows:

   **Text**: "Contoso Coffee Catalog"

   **Size:** change from 13 to 20

   **Height:** change from 40 to Parent.Height

   **Width:** change from 150 to 200

1. Using the **Align** button in the command bar (to the left of the **Color** button; alternatively, you can look for the **Text alignment** selection in the **Properties** panel on the right), change the **Align** from Align left to **Justify**.

1. Next, insert an **Image** control to **HeaderContainer1**, and adjust the properties as follows:

   **Image**: User().Image

   **Height**: Parent.Height

1. Let's create a connection icon by inserting a **Globe Icon** into **HeaderContainer1**. Adjust the properties as follows:

   **Height**: 20

   **Width**: 20

   **Color**: If(Connection.Connected, Color.Green, Color.LightSteelBlue)

1. Next, we right-justify our HeaderContainer items. To do this, look in the Properties panel on the right and look for the **Justify (horizontal)** option. The third option is **End**, go ahead and select it.

1. Finally, let's add some background color to our header container. Adjust the **Fill** property to: Color.LightSteelBlue

1. Select **MainContainer1**, where your form resides. Insert a **Button** control with the following properties:

   **Text**: "Save"

   **Width**: Parent.Width

   **OnSelect**: SubmitForm(Form1)

1. Select the form inside of MainContainer1, and adjust the **OnSuccess** property to: Navigate(Screen3)

1. From your **Tree view** panel, select **Screen3**.

1. Select the **Check** icon (iconCheck1), and update the OnSelect property to:

   `Back()`

1. Place the app in preview mode. Adjust the display to the iPhone 12 by selecting the Phone dropdown. Did you notice how your display changed the controls? Try some different tablets and phones switching orientation to see how the screen changes.

Our simple, responsive app is now usable on any platform. Way to go!
