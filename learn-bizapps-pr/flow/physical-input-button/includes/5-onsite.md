You can build a flow, which is triggered by the Flic button, that lets your manager know that you are on site.

1. Go to [Power Automate](https://flow.microsoft.com/?azure-portal=true) and sign in.

1. Select **+ Create** on the left navigation pane.

1. In the **Start from blank** area of the page, select **Automated cloud flow**.

1. In the **Flow name** field, enter **Inform manager** as the flow name. Under **Choose your flow's trigger**, search for **Flic**. Select **When a Flic is pressed** and then select **Create**.

   ![Screenshot of the inform manager flow name.](../media/inform-manager-flow-name.jpg)

1. In the Flic button trigger, select the drop-down arrow and then select the Flic button that you added previously. For **Events**, select **double-click**.

1. Select **+ New step**.

1. In **Choose an action**, search for compose and select **Compose** action.

1. In the **Inputs** field, enter your email address. Select the ellipsis (**...**) button on the upper right, select **Rename**, and then rename the action to **Email address**.

    ![Screenshot of the email compose action with Email address and Rename highlighted.](../media/add-email-compose.jpg)

1. Select **+ New step**.

1. In the **Choose an action** field, search for and select **Get manager (V2)**. In the **User (UPN)** field, select **Outputs** from **Dynamic content**.

    ![Screenshot of the Get manager action with Dynamic content and outputs highlighted.](../media/get-manager.jpg)

1. Select **+ New step**.

1. In the **Choose an action** field, search for and select the **Send an email (V2)** action.

1. In the **To:** field, select the advanced icon and then select **Mail** from **Dynamic content**. You might have to select **See more** to find **Mail**.

    ![Screenshot of the Send an email action with See more highlighted.](../media/see-more.jpg)

1. In the **Subject** field, enter **I am on site**.

1. In the **Body** field, enter **Hi**. In **Dynamic content**, select **Display Name**. In the next line, enter **I have arrived at the location**.

    ![Screenshot of the send an email action with Display name highlighted.](../media/send-email.jpg)

1. Select the **Flow checker** icon on the upper right of the screen. If no errors occur, then select **Save**.

Congratulations, you have now successfully built a flow that will trigger when you use a physical button. To test this feature, you need to have the Flic app open in your phone and then select the Flic button twice. The flow will send an email to your manager.
