Your completed and saved flow should resemble the following image.

> [!div class="mx-imgBorder"]
> [![Screenshot of the completed flow with the If yes and If no branches.](../media/17-total-flow.png)](../media/17-total-flow.png#lightbox)

In a separate tab, open the Teams app. In another tab, open the Outlook app. Now, you only need to test and run your flow. Select **Test** in the upper-right corner of the screen, select the **Manually** option, and then select **Save & Test**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Test Flow dialog with Manually selected.](../media/18-test-manually.png)](../media/18-test-manually.png#lightbox)

Open the Power Automate for desktop application. Send yourself an email with an attachment and the subject line of **New invoice**. The flow will appear with indications on each step to show where your flow is in the process.

When the Teams message appears, select **Yes**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Please approve this invoice message in Teams.](../media/19-teams-message.png)](../media/19-teams-message.png#lightbox)

Avoid interacting with your mouse or keyboard while the flow continues running because it might interrupt the process with the desktop app. When testing is complete, the following message will appear, indicating that your flow ran successfully.

> [!div class="mx-imgBorder"]
> [![Screenshot of the completed flow with the message Your flow ran successfully.](../media/20-success.png)](../media/20-success.png#lightbox)

You should also have a new email to alert you of your approved invoice. You can run the flow again and reject the invoice.

Now, you have successfully built a process that's triggered by the receipt of an email and integrates Outlook, a custom AI model, an approval in Teams, and a desktop flow.
