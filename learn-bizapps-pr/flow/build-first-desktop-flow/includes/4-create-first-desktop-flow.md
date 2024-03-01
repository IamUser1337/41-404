This unit explains how to set up a desktop flow by using the Contoso Invoicing application.

> [![Diagram of a full set of processes to create, record, and run a desktop flow, focusing on the beginning steps of creating the flow.](../media/m1-u4-process-map.png)](../media/m1-u4-process-map.png#lightbox)

Go to [Power Automate](https://flow.microsoft.com/?azure-portal=true). Ensure that you're signed in and are in the appropriate environment. Under **My flows**, select **Desktop flows > Create a desktop flow**.

> [!div class="mx-imgBorder"]
> [![Screenshot of My flows, Desktop flows, with the New desktop flow button.](../media/desktop-begin.png)](../media/desktop-begin.png#lightbox)

Select **Launch app** and then open Power Automate from the subsequent dialog. The desktop app will open in the designer with a new flow named **Untitled**, which you can change later.

Desktop flows are created to mimic the actions of a user who's performing steps in a process. You'll need to train the flow by adding those actions.

To add actions to your flow, select the desired action and then drag it to the **Main** canvas. Under the **System** dropdown menu on the Actions Pane, select and drag **Run Application**. You'll use this feature to open your invoicing application.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Run application feature under System actions.](../media/run-application.png)](../media/run-application.png#lightbox)

In the following dialog, specify the path to the application by entering the location manually; however, by selecting the icon on the right, you can select the application from a file explorer. You can search in the file explorer if you don't know the exact location of your application.

Leave the remaining fields as they are and then select **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Run application parameters with the path higlighted and the Save button.](../media/save-run-application.png)](../media/save-run-application.png#lightbox)

Now that Power Automate has opened the application, you can complete the next actions. Previously, you chose from the actions on the Action Pane; however, a simpler way of communicating actions that need to be performed is by recording your desktop. The next unit provides instructions on how you can record your desktop.
