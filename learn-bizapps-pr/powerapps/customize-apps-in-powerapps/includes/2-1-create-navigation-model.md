In this unit we'll continue to work on our Contoso Coffee Machines app, so please ensure that you have opened the app that we've continued to build in this learning module.

We're going to add some app screen navigation so that your user can move to the different screens of the app. When you build an app, the screen that is at the top of your Tree view is the screen that the app will land on, unless you deliberately define a different screen in the formula of your StartScreen for your app. In our case the first screen someone will see when we share an app with them is our 'Home Screen'.

Follow the steps below to add some navigation to our app:

1.  Go to the 'Home Screen' of your app and **Insert** two button controls.

1.  Position them both center screen, one above the other with some space between them so that our user can't accidentally tap one while trying to tap the other.

1.  Holding the Shift key, select both controls. Some controls have identical properties that are easy to align with both selected. Keep both controls selected for the next two steps.

1.  Select the **Align** dropdown control from the command bar and select "Align left". If you don't see the **Align** dropdown control in the command bar, you can right click (with both controls selected) and you'll see an **Align** option dropdown in a popup.

	> [!NOTE]
	> The **Align** feature is a powerful way to quickly line up multiple controls at once. Another powerful feature to make a note of is the **Undo** feature which is also in the command bar just to the right of the **Back** button.

1.  Now look in the Properties panel on the right and find the Width and Height properties. These are numeric input fields. Input **250** for **Width** and **100** for **Height**.

1.  Change the **Text** property of the button on top to read "View Catalog" and the **Text** property of the bottom button to read "Admin Screen".

1.  Next, we'll add our first functions that will enable screen navigation. The **Navigate** function has one required parameter, the screen that the app is going to navigate to. When you add a **Navigate** function, you enter your screen name in single quotes, and remember that Power Apps will prompt you as you type it in the formula bar. Select the "View Catalog" button, and add the following into the **OnSelect** property:

	`Navigate('Catalog Screen')`

1.  Likewise, select the button with the name "Admin Screen" and enter the following into the **OnSelect** property:

	`Navigate('Admin Screen')`

1.  Giving our user the ability to navigate from the home screen will strand them on the destination screen unless we provide a way for them to get back to the home screen. You've already seen the **Navigate** function, which you could use to get your user back to the home screen, however Power Apps has a way to get back to the previous screen your user was on through the **Back** function. Go to the **Catalog Screen** and add a **Button** control.

1. Drag your new **Button** to the bottom right corner of the screen and update the **Text** property to read "Back".

1. Now update the **OnSelect** property of your new button to the following:

	`Back()`

	This formula will return the user to the previous screen.

1. Go to your Admin Screen and repeat the two steps above.

1. Now, return to your Home Screen and place the app in preview mode. Try selecting your "View Catalog" button and then using your "Back" button to return to the home page. Try the same with your Admin Screen buttons.

> [!TIP]
> Your app will only understand Back if you first navigate to that screen through the app. If you begin to preview your app from the Catalog Screen or Admin Screen, Power Apps has no context for what screen to navigate to with the Back function. So, when you preview your app remember to start the preview from the Home Screen.

Congratulations! You have now added basic navigation to your app. If you would like to learn more about app navigation, we'll be exploring that in the next learning module. So, after a brief knowledge check, stick with us to learn some more things you can do to take your app to the next level!