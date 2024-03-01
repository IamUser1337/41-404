
While cloud flows are executed in the cloud using connectors to attach to APIs, desktop flows run on a local machine. Power Automate for Desktop is an application installed on your computer and it records Power Automate desktop flows running directly on the machine. Once created, desktop flows can be triggered manually or by cloud flows. For example, a desktop flow that automates a user’s interaction with an excel spreadsheet might be triggered manually. A desktop flow that creates an invoice is typically triggered automatically, since invoice details would likely come for somewhere else. 

Let’s take a high-level look at the process for creating a desktop flow automation. 

Desktop flows are created using the Power Automate for Desktop application. This is an application that is installed on the computer where the desktop flow is performing the operation. 
 

Like cloud flows, there are multiple desktop flow templates that you can use to help get started building desktop flows. These templates are available in the **Examples** section. Examples are broken down into common scenarios. 

In the image, you see a screenshot of the Desktop Automation examples. Examples range from beginner to advanced. 

:::image type="content" source="../media/04-describe-automation-power-automate-19.png" alt-text="Screenshot of the Desktop Automation examples." lightbox="../media/04-describe-automation-power-automate-19.png"::: 

Now you are ready to work with one of the examples, such as the flow that opens a file. You want to copy the original to ensure you don’t modify the original. 

Creating desktop flows in done in the Power Automate Desktop designer. 

:::image type="content" source="../media/04-describe-automation-power-automate-20.png" alt-text="Screenshot of the Power Automate Desktop designer, with the components indicated as per the list." lightbox="../media/04-describe-automation-power-automate-20.png":::

The designer is laid out as follows:

1. **Toolbar:** Contains basic operations for use with actions, such asSave, Undo, Copy, Debug and Paste. Also contains buttons to start the UI/Web recorders and to control the process execution, such as Start, Pause and Stop.

2. **Sub flows:** Allows you to create sub flows under your main flow.

3. **Actions pane:** Contains all Power Automate Desktop Actions and includes a search bar that helps find specific actions by matching the action name to the text string.

4. **Workspace:** Contains all the actions added to the process so far. Functions are separated into tabs.

5. **Input/output variables:** Contains all the variables you created in the process.

6. **Flow variables:** List variables created by the process.

This flow assists a user in opening files. It opens a file dialog box where the user can select a specific file to open. Once you select the file, it opens. It’s a basic example but it does help to illustrate desktop flow concepts well. 

You can add more actions by expanding an action category, selecting the action you want and then dragging the action into the workspace. In the image, we have expanded the Excel group to display a list of Excel actions. If we want a flow to open a specific excel spread sheet, we select the Launch Excel action. 

:::image type="content" source="../media/04-describe-automation-power-automate-21.png" alt-text="Screenshot of the Excel action group to display a list of Excel actions." lightbox="../media/04-describe-automation-power-automate-21.png":::

Another way to add actions is to use the recorder. The recorder lets you record the steps that you execute inside websites, on the desktop, or inside applications. As you perform actions such as opening an application and filling out data, the recorder keeps track of the steps you performed. Once you can complete the operation you want, those steps stored and saved. The steps can then be easily edited inside the designer. 

:::image type="content" source="../media/04-describe-automation-power-automate-22.png" alt-text="Screenshot of the recorded actions." lightbox="../media/04-describe-automation-power-automate-22.png":::

As you're building a desktop flow, you want to test it to ensure that it's performing as intended. You can test your flow at any time by selecting the **Run** button. The recorded steps are played back in the order they were defined in the flow. In the image, the flow is displaying an open file dialog where the user can select the file to open. 

:::image type="content" source="../media/04-describe-automation-power-automate-23.png" alt-text="Screenshot of a flow displaying an open file dialog where the user can select the file to open." lightbox="../media/04-describe-automation-power-automate-23.png":::


Once created, this desktop flow can be run manually by an individual user by selecting it in their Power Automate for Desktop app, or automatically triggered by a cloud flow. In the image, you can see an example of manually running a desktop flow from the Power Automate for Desktop application. 

:::image type="content" source="../media/04-describe-automation-power-automate-24.png" alt-text="Screenshot of running a desktop flow manually." lightbox="../media/04-describe-automation-power-automate-24.png":::


Now that we've walked through the high-level steps to create a desktop flow, let’s demonstrate the process. In the following click-through demonstration, we create a desktop flow that opens an invoice application and creates a new invoice. 

### Click-through demo: Build a Power Automate desktop flow with Copilot

In this click-through demonstration, you're guided through the process of building a desktop flow using Copilot.

[**Build a desktop flow using Copilot**](https://edxinteractivepage.blob.core.windows.net/edxpages/PL-900/m4_desktopflow_click/index.html)