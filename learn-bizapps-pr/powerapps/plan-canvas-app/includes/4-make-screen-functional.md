Now that you've designed your first screen, building the functionality for this screen is simple. The main goal is to direct users to other screens where they'll perform their purpose for visiting the app. Before you program the controls to work appropriately, you need to provide a place for the users to go. 

Start by adding a couple of blank screens by following these steps:

1. Select **New screen** and then select **Blank** twice.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Home view in Power Apps, showing the New screen menu expanded and Blank selected.](../media/new.png)](../media/new.png#lightbox)

1. Rename one screen to **Scr_EditExpense** and rename the other screen to **Scr_AllExpenses** by using the methods that you learned in the previous unit.

1. Select **Scr_Welcome** to return to your first screen.

1. Select **Btn_NewExpense_Welcome**. If you've been following this module in a single Power Apps session, then the properties dropdown menu will likely be on **Color**.

1. Change the dropdown menu to **OnSelect** (hint: it's in alphabetical order). This property sets the action of the button when a user selects it and is automatically set to **false** or do nothing.

1. Set the **OnSelect** property to **Navigate(Scr_EditExpense)**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Power Apps property dropdown menu set to OnSelect and the corresponding formula set to Navigate(Scr_EditExpense).](../media/on-select.png)](../media/on-select.png#lightbox)

1. Change the **OnSelect** property for the other button to **Navigate(Scr_AllExpenses)**. As you type, you might notice that Power Apps gives you suggestions below your formula bar. Pay attention to these suggestions because they might offer clues regarding what the formula needs. Additionally, you can select the suggestions to make building faster. Other than offering suggestions below the formula bar, Power Apps will also offer hints above the formula bar to provide explanation about what the formula needs or does.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Navigate formula, showing suggestions after you type Navigate(.](../media/navigate.png)](../media/navigate.png#lightbox)

1. Hold down the **Alt** key on your keyboard and then select one of the buttons to observe the **OnSelect** property in action.

Now, you've completed the functionality of your welcome screen. Let's review decisions made throughout this module.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWQF6A]
