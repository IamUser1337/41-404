## Mouse actions

To locate the current position of the cursor and retrieve its coordinates, use the **Get Mouse Position** action. Measure the position from either the top-left corner of the screen or the top-left corner of the foreground window. The action measures the cursor's coordinates as mouse position x and y and stores them into two separate variables.

![Screenshot of the Get mouse position action properties dialog.](..\media\mouse-position-action-properties.png)

To move the mouse to a specified position, use the **Move Mouse** action. Specify the target coordinates and how fast to move the cursor. Calculate the coordinates from the top left of the screen, the currently active window, or the mouse's current position. Set the mouse to move to the new position instantly, where the mouse appears to jump from one position to another or use animation to simulate a user's movement of the mouse. Optionally adjust the speed of the animation. To capture the current coordinates of the mouse relative to the screen, press **Ctrl** + **Shift**. This will populate the Position X and Position Y fields.

![Screenshot of the Move mouse action properties dialog.](..\media\move-mouse-properties.png)

Specify an image on the screen to move the cursor to with the **Move Mouse to Image** action. Select the target image from existing images. If no images have been added, they can be captured by clicking on the **Capture image** button in the pop-out.

![Screenshot of the Move Mouse to Image properties dialog pop-out.](..\media\move-mouse-image-properties-popout.png)

Use this action to add multiple images. When an action includes multiple images, it will move the mouse to the first image found. The callouts in the following screenshot show how to configure multiple images:

1. Determine the mouse movement's animation type and speed.
1. Determine which occurrence of the image the action should move the mouse to.
1. Send a left mouse click after moving the cursor to the image. Set the click to occur immediately after the cursor has been moved to the image or specify a delay in seconds.

   ![Screenshot of the Move mouse to image action properties.](..\media\move-mouse-image-action-properties.png)

1. Set the action to wait for the image to appear onscreen as well as a duration for the wait
1. Determine which algorithm to use when searching for the image.
1. Use the graphical tool to determine which part of the image the cursor moves to; center, left, middle, upper right etc.
1. Use the x and y offset fields to further modify this selection.
1. Use the tolerance field to allow for some difference between the captured image and the actual image the action will search for. The higher the tolerance, the more likely the action will be to identify the offscreen image, even if it differs from the one captured. The tolerance is measured on a scale of 0 to 128.
1. Specify whether the action should search for the image on the entire screen or only on the foreground window
1. Further narrow down the search area to include only a subregion of the screen or window
1. Select Subregion to capture an area of the screen or active window. The subregion uses four coordinates that specify a rectangular area on the screen or window.
1. Optionally, store the coordinates of the image found in two separate variables

   ![Screenshot of the Move mouse to image action advanced properties.](..\media\move-mouse-image-action-properties-advanced.png)

Specify a string of text on the screen to move the cursor to with the **Move Mouse to Text on screen**. The action moves the cursor to the text, even if it is stored as an image such as a jpg or pdf file. For this action, you must specify an optical character recognition (OCR) engine or an OCR engine variable. The callouts in the following illustration show how to configure this action.

1. In the action properties, set the OCR engine type, or specify a previously created OCR engine variable
1. Text to Find is a required input. Optionally enter a regular expression
1. In case the text appears more than once on the screen, specify which occurrence of the text to move the cursor to
1. Specify whether the action should search for the text on the entire screen, or only in the foreground window
1. Specify a subregion relative to an image
1. As with the previous actions, determine the speed of the mouse movement
   
   ![Screenshot of the Move Mouse to Text on Screen action properties dialog.](..\media\move-mouse-text-screen-action-properties.png)

1. Determine whether the action should wait for an image to appear onscreen and for how long to wait before it fails
1. Select whether to send a left mouse click after moving the cursor to the image. The click can occur immediately upon the cursor moving to the image or it can be delayed by a number of seconds.
1. Determine whether the cursor should move to the center or another area of the text
1. The X offset for the cursor's position relative to the text as specified in step 9
1. The Y offset for the cursor's position relative to the text as specified in step 9
1. The action creates four output variables; two that store the coordinates of the text found on screen
1. The other two hold the dimensions of the area occupied by the text in pixels

   ![Screenshot of the Move Mouse to Text on Screen action advanced properties dialog.](..\media\move-mouse-text-screen-action-properties-advanced.png)  

To simulate mouse click(s), use the **Send Mouse Click**. Choose whether the action should wait a number of milliseconds before sending the click. Unless otherwise configured, the action sends the mouse click at whatever position on screen the cursor happens to be when the flow runs this action. Check Move mouse before sending mouse event to show the options of the Move Mouse action. A variable can be used for entering the coordinates. Set the coordinates relative to the entire screen, the active window or the current mouse position. To enter the cursor's current position into the coordinates, press CTRL+SHIFT. As with all mouse actions, determine the speed and animation type.

![Screenshot of the Send Mouse Click action properties dialog.](..\media\send-mouse-click-action.png)

## Keyboard actions

Simulate using the physical keyboard to enter text or other key commands with the **Send Keys** action. Enter the text to send or specify a text variable. Additionally, set **Direct sensitive text input** to hide the text in the action properties. Select the "eye" icon to show the text you entered. For more specialized key commands, use the **Insert special key** button to keys such as the arrow keys, Caps Lock or keys from the numeric keypad, and **Insert modifier** to send keys such as Shift and Control. Optionally, set a delay between the keystrokes in milliseconds. 

![Screenshot of the Send Keys action properties dialog.](..\media\send-keys-action.png)

> [!NOTE]
> To send a key, rather than text, use curly brackets, and capitalize it. For example: Entering {Control}({A}) in Text to Send will perform the Select All function.

Combine mouse and keyboard actions to perform more advanced gestures, such as Control+click or Shift+click with the **Press/Release Key** action. Configure the action to simulate pressing and holding one or any combination of the keys Control, Alt, Shift and/or the Windows key.

![Screenshot of the Press Release Key action properties dialog.](..\media\press-release-key-properties.png)

> [!WARNING]
> The pressed key state persists after the flow has finished and the computer will behave as if the key is still pressed. You must use another Press/Release Key action must be used to revert the key to its default state.

To enable or disable Caps Lock, Num Lock and Scroll Lock, use the **Set Key State** action.

![Screenshot of the Set Key State action properties dialog.](..\media\set-key-state-action.png)

To ignore mouse or keyboard input from the user while the flow is running, use the **Block Input** action.

![Screenshot of the Block Input action properties dialog.](..\media\block-input-action.png)

> [!WARNING]
> To re-enable user input, add another Block Input action to the flow, and set it to Unblock Input. For this to take effect, run Power Automate for desktop with Administrator rights.
