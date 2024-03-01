Design a flow that navigates to the properties of the current computer, takes a screenshot of the properties window, and saves it on the desktop.

The flow will:

* Retrieve the location of the current user’s desktop folder
* Navigate to this PC by using the Start Menu
* Open the properties of this PC
* Take a screenshot of the window and save it on the desktop

1. Use the **Get special folder action**. Under **Special folder name**, select **Desktop**.

    ![Screenshot of the Get special folder action properties dialog.](..\media\get-special-folder-exercise-part-one.png)

1. Use the **Move mouse** action. Set the coordinates of the Start button, and set **Move mouse from previous position** to **With animation (high speed)**.

    ![Screenshot of the Move mouse action properties dialog.](..\media\move-mouse-exercise-part-two.png)

> [!NOTE]
> To capture the current coordinates of the mouse relative to the screen, press **Ctrl** + **Shift**. This will populate the Position X and Position Y fields.

1. Add the **Send Mouse Click** action. Leave the **Mouse event to send** option on its default setting, Left Click.

    ![Screenshot of the Send mouse click action properties dialog.](..\media\send-mouse-click-exercise-part-three.png)

1. Add the **Send keys** action. In **Text to send** enter **This PC{Enter}{Apps}{R}** and set **Delay between keystrokes** to **500**.

    ![Screenshot of the Send keys action properties dialog.](..\media\send-keys-exercise-part-four.png)

    * This PC will type the text “This PC” into the Start Menu search
    * {Enter} will simulate pressing the enter key to open this PC
    * {Apps} will open the context menu in the PC window
    * {R} will select and open properties

     ![Screenshot of the Take screenshot action properties dialog.](..\media\take-screenshot-exercise-part-five.png)

1. Add the **Take screenshot** action. Set **Capture** to **Foreground window**, **Save screenshot to** to **File**, **Image file** to **%SpecialFolderPath%\screen.jpg** and **Image format** to **JPG**.

1. Running the flow will result in the screen.jpg file being placed on the current user’s desktop.
