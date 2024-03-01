The **Configure run after** option and email notification is beneficial in helping you swiftly resolve issues with your workflow run.

## Use the Configure run after option to handle errors

With the **Configure run after** option, you can identify which step failed and, if it did, bring that to your attention. The setting **is successful,** in the notification is the default; however, you would use the **has failed** setting to handle errors.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Configure run after option with "is successful" selected.](../media/configure-run-after.jpg)](../media/configure-run-after.jpg#lightbox)

Consider a scenario where, after you have uploaded an image to a SharePoint library, you decide to send it to Microsoft Azure Cognitive Services, an AI and machine learning service, to analyze the image. After the image has been analyzed, you can save all tags that were created by Cognitive Services in SharePoint if you set up a workflow.

The first step is to send the image, or the file content, to the **Analyze Image** action in the flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Analyze Image action in the flow.](../media/analyze-image.png)](../media/analyze-image.png#lightbox)

Because multiple tags have been received, they're first added to an array variable, and the variable is saved in a property column in the SharePoint library.

## Add a parallel branch for immediate notification

Adding a parallel branch allows you to add a mobile or email notification step to inform the maker of the flow in which an issue has occurred.

The following image shows that, after the **Analyze Image** action, a parallel branch has been added.

> [!div class="mx-imgBorder"]
> [![Screenshot of the plus sign below Analyze Image with Add a parallel branch highlighted.](../media/add-parallel-branch.jpg)](../media/add-parallel-branch.jpg#lightbox)

A **Send me an email notification** parallel step has been selected.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Choose an operation dialog box for the parallel branch with search results for notification highlighted.](../media/notification-options.jpg)](../media/notification-options.jpg#lightbox)

In the **Configure run after** action for the email notification step, the **has failed**, **is skipped**, and **has timed out** settings are selected.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Send me an email notification action with the ellpsis button selected to reveal the Configure run after option.](../media/notification.png)](../media/notification.png#lightbox)

> [!NOTE]
> This action is directly tied to the success of the previous step, which in this case is **Analyze Image**, as shown by the following screenshot.
>
> [!div class="mx-imgBorder"]
> [![Screenshot of the Configure run after option with three settings selected.](../media/configure-run-after-options.jpg)](../media/configure-run-after-options.jpg#lightbox)

Now, you've successfully added a step to handle errors that the **Analyze Image** action might encounter. You can repeat this error handling step for other important actions.

## Use Parse JSON to get the current flow run information

If you call **workflow()** in Power Automate, you get a JSON object that contains information about the Flow and the instance, including the current environment guid, Flow name, Flow guid and run ID.
 
You can then parse that information and build a URL out of it. So if an action fails, you can **configure run after** an email action (explained above), and have a link directly to that flow action.

> [!div class="mx-imgBorder"]
> [![Screenshot of the workflow information.](../media/workflow.svg)](../media/workflow.svg#lightbox)

For more information about the **workflow()** function, see [Power Automate Workflow function](/azure/logic-apps/workflow-definition-language-functions-reference?azure-portal=true#workflow)