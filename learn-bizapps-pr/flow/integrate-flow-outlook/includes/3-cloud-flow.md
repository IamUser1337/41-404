Now that you have a desktop flow, you're ready to create a solution in Power Automate. Solutions are groups of apps and flows that are packaged together and enable seamless application lifecycle management (ALM). For example, when you host your flow in a solution, both become portable, making it effortless to move them and all their components from one environment to another, in other words, from development to production. Flows that are built inside solutions are called solution-aware flows. Be aware that you can't move a non solution-aware flow into a solution, so if you think that you'll need a solution, start with one from the beginning to avoid needing to rebuild your flow. 

Watch the following demo video of the steps that you'll complete in this unit.

 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5cV2R]

Go to [Power Automate](https://powerautomate.microsoft.com/en-us/) to get started, select **Solutions** on the left navigation menu, and then select **New solution**. 

> [!div class="mx-imgBorder"]
> [![Screenshot of the New solution button on the Solutions window.](../media/new-solution.png)](../media/new-solution.png#lightbox)

Set the display name for your solution. In this case, the display name is **Invoice processing solution**, but you can choose whatever fits your needs. Notice that the name fills in automatically as you set the display name. Solutions are built on Microsoft Dataverse, and the names can't use spaces, which allows for easier calling inside of other apps and solution-aware flows. Set the publisher as **CDS Default Publisher** and then select **Create**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the solution details on the New solution screen.](../media/create-solution.png)](../media/create-solution.png#lightbox)

The **Solutions** screen will populate with your new solution. Select the name (in this case **Invoice processing solution**) to open it.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Invoice processing solution name selected.](../media/open-solution.png)](../media/open-solution.png#lightbox)

This screen is where you'll create and edit flows that are specific to this solution. To create a new solution-aware flow, select **Cloud flows > Automation > Cloud flow > Automated**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Cloud flow selected in the new menu.](../media/cloud-flow.png)](../media/cloud-flow.png#lightbox)

Name your flow. The following flow has been named **Use Outlook email trigger Desktop flow**, but you can choose whatever name you want. Search the actions to find and select **When a new email arrives (V3)** and then select **Create**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow named and the action of When a new email arrives (V3) selected.](../media/new-email.png)](../media/new-email.png#lightbox)

Always use the latest version of the action that you're seeking, which will ensure that you have access to new features that have been released.

You might need to wait a moment for Outlook to sign in. The **Folder** option should display and be automatically populated with **Inbox**. Select **Show advanced options** and then ensure that **Include Attachments** and **Only with Attachments** have **Yes** selected. In the **Subject Filter** field, enter **new invoice**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Show advanced options feature.](../media/show-advanced-options.png)](../media/show-advanced-options.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of the attachment options fields.](../media/attachment-options.png)](../media/attachment-options.png#lightbox)

Select **New step** and then search for and select the **Run a flow built with Power Automate for desktop** action.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Run a flow built with Power Automate for desktop action.](../media/run-desktop-flow.png)](../media/run-desktop-flow.png#lightbox)

If you haven't already set up your gateway connection, use the **Gateway name** dropdown menu to select the appropriate gateway.

If your gateway doesn't appear, you might need to delete this step and re-create it to refresh the list. If your gateway still doesn't appear, you might need to restart the gateway on your PC and then retry the process.

The next two fields will request your credentials to sign in to your computer. If you're uncertain about what to put in the **Domain and username** field, you can open a command prompt window by opening the **Start** menu, entering **CMD** in the search box, and then pressing the **Enter** key. When the command prompt opens, enter **Set user** and then press the **Enter** key.

Several lines of code will appear. Separate the **user domain** and the **username** with a backslash (\\), as shown in the following screenshot. Select **Create**.

> [!div class="mx-imgBorder"]
> [![Screenshot of desktop flow details.](../media/user-domain-user-name.png)](../media/user-domain-user-name.png#lightbox)

After you've connected to your desktop, Power Automate will prompt you for information that's specific to your desktop flow. Use the dropdown menu to select the name of your desired flow (in this case, **Invoicing**), and then in the **Run Mode** dropdown menu, select **Attended - Runs when you're signed in**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Desktop flow and Run Mode dropdown menus.](../media/choose-desktop-flow.png)](../media/choose-desktop-flow.png#lightbox)

When you've chosen your desktop flow, the input variables that you've defined in your flow will be requested. The following screenshot shows that the invoice flow is requesting an **Amount**, a **Contact email**, and an **Account name** to feed into the Contoso Invoicing app. Put some placeholders in these fields for now, though you can use information from the email or attachments later. You can also use the output variables that are provided by the desktop flow in later actions. **Save** your flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of placeholders entered for Amount, Contact email, and Account name fields.](../media/placeholders.png)](../media/placeholders.png#lightbox)

Now that you've set up your desktop connection and have created a cloud flow to trigger your desktop flow and provide inputs, you can test that everything is functioning properly.
