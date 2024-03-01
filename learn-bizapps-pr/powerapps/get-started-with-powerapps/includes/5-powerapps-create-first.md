In the following exercise, we're going to create your first app with an Excel table as the data source. We can use any Excel table as a data source if you formatted the data as a table and saved it to a data source that you have access to, such as OneDrive. In this exercise, we're going to download the data, save it to OneDrive, make a quick three-screen app, and then begin creating an app on a blank canvas. The app we begin creating from a blank screen in this exercise will be the one that we continue with in future learning units. The three-screen app is yours for reference so you can see how controls interact with each other to access your data. Both apps are able to interact with the same data.

## Get the data

Download the Excel spreadsheet [CoffeeMachineData.xlsx](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-apps/coffee-machine-data/CoffeeMachineData.xlsx). Select the link and then the **Download raw file** button to download the file. Once it downloads, continue with these steps.

1. From your OneDrive browser tab, select **Add new** > **Files upload**.

1. In the Open popup, select the location of CoffeeMachineData.xlsx file, most likely in your Downloads folder.

1. Once you find and select the CoffeeMachineData.xlsx file, select **Open**. Confirm that the file is in your OneDrive by entering CoffeeMachineData in the search field in the top center of the OneDrive command bar. Now that you have the data file in your OneDrive, let's build the app.

## Build a three-screen app

Let's start by building a three-screen app that Power Apps can make in just a few button clicks.

1. Return to the Power Apps Maker Portal [make.powerapps.com](https://make.powerapps.com/?azure-portal=true) and sign in with your organizational account.

1. Select the **Create** tab from the left-side menu.

1. Pick the **Excel** button under the **Start from** options.

1. If you don't see your OneDrive for business connection under **Connections**, select the **+New connection** button, then the **Create** button to create the connection. Once it's there, select your **OneDrive for Business** connection.

1. Under **Choose an Excel file**, find and select CoffeeMachineData.xlsx. You can search for it by using the search field in the upper right corner.

1. Under **Choose a table**, select CoffeeMachines. CoffeeMachines is the table where the app data resides.

1. Select the **Connect** button on the bottom right and watch as Power Apps builds a three-screen app.

   In just a few moments, Power Apps shows you a fully functional app with a mobile look to it. To get an idea of what it looks like on your mobile device, use the preview button that looks like a "play" button on the upper right near a "save" icon. Select the "play" button (or press F5) and try out the interface.

   Notice that you can scroll through the list of items, select an item, see some item details, edit item details, and save/cancel your changes. When you build an app with the Excel button, you quickly can have a fully functional app.

   Let's exit the preview mode by pressing the X in the upper right corner, and then save this app.

1. Select the **Save** button and enter a name for this app in the **Save as** pane. Then select **Save**.

1. Select the **Back** button from the top left of the command bar, to exit the app.

Now that you experienced Power Apps making an app for you, let's begin building our own app.

## Create a Canvas app

1. Starting from the Power Apps Maker Portal (make.powerapps.com), select the **Create** tab, and then select **Blank app**.

1. In the **Create** popup window, under **Blank canvas app** select **Create**.

1. **Name** your app "Contoso Coffee Machines" and leave the Format toggle selected to **Tablet**. Select **Create**.

1. You now see a blank screen with a Welcome to Power Apps Studio popup or a message on your screen. It prompts you to "Add an item from the Insert pane or connect to data." We begin by creating a gallery to view our data records. Select the gallery option. If you don't see this popup, then select the **Insert** button from the command bar, and find/select **Vertical gallery**.

1. A control called **Gallery1** appears on your screen. It isn't currently connected to data, so Power Apps prompts us to **Select a data source**. With all the different types of data, we need to tell Power Apps what type of data we want to connect to. In this case, we need to connect to the Excel spreadsheet that we saved to OneDrive. We accomplish it with the **OneDrive for Business** connection. This connection allows us to access documents from our business OneDrive account, and any SharePoint document library that we have access to.

1. Find/select **OneDrive for Business.** You can enter OneDrive in the search field to quickly locate it. You might need to then select **Add a connection** and authenticate your connection to it.

1. Once you complete the connection to **OneDrive for Business**, a panel appears on the right side of the screen prompting you to **Choose an Excel file**. Find and select the Excel document that we copied to our OneDrive for Business called "CoffeeMachineData.xlsx." If you're having trouble finding it, you can enter the file name in the search field to narrow the choices.

1. After you select the "CoffeeMachineData.xlsx", the panel now prompts you to **Choose a table**. There should be a single option of "CoffeeMachines." Select the box next to "CoffeeMachines" and then select the **Connect** button from the bottom of the panel.

1. Select your gallery once more. On the right side of the screen is a **Properties** panel for your gallery control. Ensure that the **Data source** is set to your CoffeeMachines. If you didn't already see the gallery populating with a picture, title, and price, you should be seeing that now.

1. Resize your gallery to stretch to the bottom of the screen and to touch the left side of the screen.

1. Now let's add a form control so we can update the data displayed in our gallery. Select the **Insert** button from the header menu. Find and select **Edit form**.

1. The control **Form1** appears on your screen. Drag it to the right half of your screen and reposition and resize it so that it takes up the right half of your screen.

1. Notice that our new form prompts us to **Connect to data**. With the form control selected, look at the **Properties** panel on the right side of the screen. Directly under **Properties**, you see **Data source** and a dropdown saying **None**. Select the dropdown and select your **CoffeeMachines** table.

1. Let's add fields to our form, since it's currently blank. In the **Properties** panel, select the link to **Edit fields**, it's just below the Data source dropdown.

1. In the **Fields** popup panel, select the **Add field** button.

1. Check the box next to each of the fields under **Choose a field**. Then select **Add**. Your form now shows input fields arrayed in a three-column form. All the fields should be blank.

1. Next, we need to designate which item of our data to display in the form. Look at the Gallery control on the left of your screen. The Gallery shows all the coffee makers, so we want our form to show one of these. With your form selected, go to the formula (***fx)*** bar at the top of the screen. To the left of the formula bar, there's a dropdown to find the properties for the Form control. Select the dropdown and find/select the **Item** property.

1. In the Item field in the ***fx*** formula input box, enter **Gallery1.Selected**. You should immediately see data populating the fields of your form.

1. You can preview your app at any time by selecting the "Play" icon from the top right of the command bar, pressing the F5 function key, or simply by selecting and holding the **Alt** key on your keyboard. With your app in preview mode, try scrolling through your gallery and selecting a few different coffee makers. Observe how it populates the form based on the item you select.

1. Next, let's add a button control so that we can save any changes we make to the data. Select the **Insert** button from the command bar and find/select **Button**.

1. Let's change the button text from "Button" to "Save." In the Properties panel on the right, the first item is the Text property. Replace "Button" with "Save" and enter it.

1. Reposition your new button control under your form at the bottom of the screen.

1. With your button control selected, go up to the ***fx*** formula bar. Change the **OnSelect** property from "false" to read **SubmitForm(Form1)**.

1. Now, place your app in **Preview** mode again. And update one of the fields in your form, such as the Machine Price. Press your **Save** button to record the changes.

1. Next let's add a header for your app. Select the Insert button again and find/select a **Rectangle** control.

1. Place the rectangle control in the top left corner of your screen and stretch it out so that it goes all the way to the right side of the screen. In the properties panel for your rectangle, find the **Height** input field and enter 75.

   > [!TIP]
   > Any item in the properties panel has a corresponding value viewable in the formula (***fx***) bar. If you can't find it in the properties panel, you can select the dropdown just to the left of the formula bar input field. In this case you could find/select the Height property.

1. Now resize your gallery and form controls so that they fit just under the rectangle.

1. Insert a **Text label** control. Change the **Text** property to read "Contoso Coffee Machines."

1. Next adjust the **Size** of your label control to be 24, and then resize the control so that the title fits on a single line.

1. We change the font color next. You can change it by selecting the **Color** setting in the command bar. Under **Standard colors**, select the circle that is white.

1. Finally, reposition your label control so that it's centered in the middle of the screen in the middle of the rectangle. Notice how dashed lines appear as you approach the center of your screen to help you align the label.

So, there you go! You created a single-screen app from a blank screen that enables you to update and save any of the data in your Coffee Machine data. In the next unit, we'll continue to build onto this app as we learn new concepts.
