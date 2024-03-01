In this section, you discover how to install your AI Builder flows to fulfill your business scenarios.

## Prerequisites

- Access to [Power Automate](https://flow.microsoft.com/?azure-portal=true).
- A license or trial of the [AI Builder](/ai-builder/administer-licensing).
- An [environment](/power-platform/admin/environments-overview) with a [Microsoft Dataverse database](/power-platform/admin/create-database). (Applicable only for work or school accounts).
- A basic understanding of Power Automate and experience with creating a flow is recommended.

## AI Builder flow templates

[Power Automate templates](https://us.flow.microsoft.com/templates/?azure-portal=true) contain preconfigured logic that eases creation of flows for specific business purposes.

To create a flow from an AI Builder template, follow these steps:

1. Select the **Templates** in the left menu. The list of available templates appears.

1. Enter **AI Builder** in the search bar and then press the **Enter** key. All AI Builder templates are displayed, as shown in the following figure.

    > [!div class="mx-imgBorder"]
    > ![A screenshot of a search for A I Builder showing all flow templates.](../media/templates.svg)

1. Select the **Send a notification with the sentiment of manager's email using AI Builder** template. You see a summary of the template with a list of the connections that it uses.

    ![Screenshot of sending a notification with the sentiment of manager's email using A I Builder.](../media/notification.svg)

1. At the bottom, select **Continue**.

1. A preconfigured flow appears (at this stage, the flow isn't yet saved).

    > [!div class="mx-imgBorder"]
    > ![Screenshot of a preconfigured flow template with If yes and If no conditions.](../media/preconfigured-flow.svg)

    You can save the flow as-is or update it at your convenience:

    - Modify existing actions: input parameters, action name, or advanced parameters
    - Add new actions
    - Remove existing actions (this step is likely to break the actions downstream)

1. Once you're done, select **Save** and then you can test the flow.

## Create a flow from AI Builder studio

From AI Builder studio, you can launch the creation of a flow by using your favorite model.

The following example shows a custom document processing model. The detail page of the model contains a **Use model** button (the model must be published). Selecting this button opens a right panel that offers multiple options, as shown in the following figure.

> [!div class="mx-imgBorder"]
> ![Screenshot of custom document processing model with Use model button selected to reveal the User your model panel to the right.](../media/custom-form.svg)

Selecting **+ Build intelligent automation** and then **Other** opens the screen where you can create a flow from a template.

![Screenshot of select a button to read and save information from documents using A I Builder.](../media/new-flow.svg)

Selecting **Continue** opens a preconfigured flow with the custom model selected in the AI Builder action.

> [!div class="mx-imgBorder"]
> [![Screenshot of select continue to open Process and save information from forms flow.](../media/continue-flows.svg)](../media/continue-flows.svg#lightbox)
