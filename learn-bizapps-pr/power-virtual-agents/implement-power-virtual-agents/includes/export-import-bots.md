You can export and import bots using solutions to move your bots across multiple environments. For example, you may build your chatbot in a development environment, then move it to a different environment for testing purposes. Once the testing is complete, you can move it to a production environment for the chatbot to be deployed to end users.

Solutions are the mechanism for implementing application lifecycle management (ALM). The solution acts as a carrier for the bots. You use solutions to export the bot from one environment and import it into another. For more information, see [Solutions.](/power-apps/maker/data-platform/solutions-overview/?azure-portal=true)

## Export your bot

You can add a chatbot to an existing solution or create a new solution for your chatbot from Power Apps Solutions.

1. In your browser navigate to the Power Apps maker portal, [make.powerapps.com.](https://make.powerapps.com/)

1. On the left-hand side, select **Solutions**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Power Apps Solutions highlighted.](../media/solutions.svg)](../media/solutions.svg#lightbox)

1. Select the solution you would like to add the chat bot to.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Power Apps Solutions page with the New solution button and Customer service bot highlighted.](../media/solution-select.svg)](../media/solution-select.svg#lightbox)

1. Within the solution, choose the bots you would like to add by clicking **Add existing** > **Chatbot**. Multiple chatbots can be added to a single solution.

	> [!Note]
	> It is also possible to create a new chatbot from solutions.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Power Apps solution with the Add existing menu expanded and Chatbot selected.](../media/add-existing.png)](../media/add-existing.png#lightbox)

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Power Apps Add existing chatbots dialog showing the list of existing chatbots.](../media/existing.png)](../media/existing.png#lightbox)
	
	> [!Note]
	> Subcomponents of the bot will be added to the solution, such as topics, entities, and cloud flows. You shouldn't  remove or change any of the bot subcomponents from Power Apps as this can cause the export to fail.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Power Apps showing a list of all the customer service bot's subcomponents.](../media/components.png)](../media/components.png#lightbox)
	
	> [!Note]
	> If you add more components to your bot, such as creating new topics, you can add these to the solution by selecting **Add required components** from the chatbot in the solution as shown below.
	
	> [!div class="mx-imgBorder"]
	> [![Screenshot of the list of customer service bot components with the customer support component selected to show the Add required components option.](../media/add-required.png)](../media/add-required.png#lightbox)

1. Once your solution is ready, you can export the package. Go back to all solutions by selecting the **Back to solutions** arrow on the left pane.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the back to solutions button.](../media/back-solutions.svg)](../media/back-solutions.svg#lightbox)

1. Select the circle next to the solution name that you would like to export. 

1. Select the **Export** button at the top.

1. Select **Next** on the export pane, and then select **Export.**

This will download a .zip file of the solution, which will be used for importing the bot into another environment. If you're moving your bot to a test or production environment, you should export as a managed solution.

For more information, see [Export solutions](/power-apps/maker/data-platform/export-solutions/?azure-portal=true).

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Apps solutions list showing customer service bot selected and the export button highlighted.](../media/export.svg)](../media/export.svg#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Apps showing the message Solution "customer service bot" exported successfully and will download soon, and the downloads dialog.](../media/download.svg)](../media/download.svg#lightbox)

## Import your bot

You'll use the solution package downloaded at the export stage to import your bot into the desired environment. It's imported from Power Apps Solutions.

1. In the top right, select your environment name and change to the desired environment to import the solution and chat bot.

1. On the left-hand side, select **Solutions**

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Power Apps Solutions.](../media/solutions.svg)](../media/solutions.svg#lightbox)

1. Select **Import**, and select your solution .zip file.

1. Select **Next** and then **Import.**

For more information, see [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions/?azure-portal=true).

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Apps solutions page with the import button highlighted.](../media/import.svg)](../media/import.svg#lightbox)

Once the import is complete, you'll see it appear in your solutions list. You can access your imported bot from Microsoft Copilot Studio as it will now appear in your list of bots in the new environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Apps with the message Solution "Customer service bot" imported successfully.](../media/imported.svg)](../media/imported.svg#lightbox)

