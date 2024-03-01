In this exercise, you set up the mobile App ID and the mobile URL environment variables.

  > [!NOTE]
  > This setup is specific only for setting up Store Operations Assist Mobile within Microsoft Teams. 

## Task - Set up the mobile App ID environment variable

As Oscar, the Microsoft Power Platform administrator, you need to set up the mobile App ID so that store associates can navigate from Store Operations Assist Teams to Store Operations Assist Mobile.

1. Sign in to [Power Apps](https://make.preview.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Ensure that you're in the correct environment.

1. Select **Apps** in the left navigation pane, select **Store Operations Assist Mobile**, and then select **Details** from the **More Commands (...)** dropdown menu.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of Details selected from the More Commands menu.](../media/details.png)](../media/details.png#lightbox)

1. Copy the **App ID** and then save it for use in a later step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the App ID highlighted.](../media/app-id.png)](../media/app-id.png#lightbox)

1. Select **Solutions** in the left navigation pane.

1. In the search area, search for **Default**. Select **Default Solution**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Default Solution option selected.](../media/default-solution.png)](../media/default-solution.png#lightbox)

1. Select **Environment variables** and then select **SOAMobileAppID**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of environment variables with S O A Mobile App I D selected.](../media/environment-variables.png)](../media/environment-variables.png#lightbox)

1. In the right pane, select **+ New value** under **Current Value**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the New value button.](../media/new-value.png)](../media/new-value.png#lightbox)

1. Paste the copied App ID in the **Current Value** field for the **SOAMobileAppID** environment variable. Select **Save**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the Save button to save the copied App I D.](../media/save-button.png)](../media/save-button.png#lightbox)

## Task - Set up the mobile URL environment variable

As Oscar, the Microsoft Power Platform administrator, you need to set up the URL of the Store Operations Assist environment that you want your store associates to access through Teams.

1. Sign in to [Power Apps](https://make.preview.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Ensure that you're in the correct environment.

1. To get the app URL, go to **Settings > Session details**.

1. Copy the instance URL without the **https://www** part and the last forward slash (**/**) and then save it for use in a later step.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the instance URL.](../media/instance.png)](../media/instance.png#lightbox)

1. Select **Solutions** in the left navigation pane.

1. In the search area, search for **Default**. Select **Default Solution**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the default search results.](../media/solution-default.png)](../media/solution-default.png#lightbox)

1. Select **Environment variables** and then select **SOAMobileURL**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the mobile U R L environment variable.](../media/mobile.png)](../media/mobile.png#lightbox)

1. In the right pane, select **+ New value** under **Current Value**.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the New value button under the Current Value area.](../media/value-new.png)](../media/value-new.png#lightbox)

1. Paste the copied URL in the current value for the **SOAMobileURL** environment variable. Select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the save value button.](../media/save-value.png)](../media/save-value.png#lightbox)

