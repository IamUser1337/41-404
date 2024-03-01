Occasionally, you have to deal with last-minute meetings. In this situation, it would be beneficial to have the ability to quickly show your calendar as busy. This exercise will walk you through the steps of using the Flic button to block your Outlook calendar for an hour.

1.  Go to [Power Automate](https://flow.microsoft.com/?azure-portal=true) and sign in.

1.  Select **+ Create** from the left navigation pane.

1.  In the **Start from blank** area, select **Automated flow**.

1.  In the **Flow name** field, enter **Block my calendar** as the flow name. Under **Choose your flow's trigger**, search for Flic. Select **When a Flic is pressed** and then select **Create**.

1.  In the Flic button trigger, select your configured button. For **Events**, select **hold**.

1.  Select **+ New step**.

1.  In the **Choose an action** field, search for and select **Create event (V4)**.

1.  For **Calendar id** select **Calendar.**

1.  For **Subject**, enter **Out of office.**

1. In the **Start Time** field, select **Expression** and then enter **utc**. Select the **utcNow** option and then select **OK**.

1. In the **End time** field, select **Expression** and then enter the **addHours(utcNow(),1)** formula. Select **OK**.

1. Select your **Time zone**

1. Select the **Flow checker** icon on the upper right of the screen. If no errors occur, select **Save**.

1. Congratulations, you have now successfully built a flow that will trigger when you use a physical button. Holding the button will automatically block your Outlook calendar for an hour.

