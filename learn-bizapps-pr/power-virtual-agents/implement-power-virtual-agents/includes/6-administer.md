Microsoft Copilot Studio gives you the flexibility to administer analytics and manage security of the chatbots.

## Analytics

The analytics section is divided into numerous pages to give you multiple ways to understand bot performance.

The **Summary** tab provides a detailed overview of how many total chatbot sessions were run over the period that you selected. Information such as total number of sessions, engagement rate, resolution rate, escalation rate, and abandon rate can help you to understand how effective the bot has been and to determine the areas that need improvement.

> [!div class="mx-imgBorder"]
> [![Analytics section showing the Summary tab for the last seven days.](../media/analytics.png)](../media/analytics.png#lightbox)

The **Customer Satisfaction** report helps identify which topics are having the most impact and where analysts will go to stay informed.

> [!div class="mx-imgBorder"]
> [![Monitoring Microsoft Power Platform: Microsoft Copilot Studio Analytics.](../media/customer-satisfaction.png)](../media/customer-satisfaction.png#lightbox)

The **Sessions** tab gives you the flexibility to download raw data from all chatbot sessions. This offering includes a complete transcript of the sessions and the outcome.

> [!div class="mx-imgBorder"]
> [![Sessions csv file in Microsoft Excel showing session data.](../media/sessions.png)](../media/sessions.png#lightbox)

The **Billing** tab shows the billable interaction between a customer and a bot and represents one unit of consumption. The billed session begins when a user topic is triggered.

A session will end for one of the following reasons:

- The user ends the chat session. When the bot doesn't receive a new message for more than 30 minutes, the session is considered closed.

- The session is longer than 60 minutes. The first message that occurs after 60 minutes starts a new session.

- The session has more than 100 turns. A turn is defined as one exchange between a user and the bot. The one-hundred-and-first turn starts a new session.

> [!div class="mx-imgBorder"]
> [![Analytics with the Billing tab selected showing billed sessions for the last seven days.](../media/analytics-billing.png)](../media/analytics-billing.png#lightbox)

## Security

You can set up other security measures for your bot and your users.

> [!div class="mx-imgBorder"]
> [![Security showing tiles for Sharing, Access, Authentication, and Web channel security.](../media/security.png)](../media/security.png#lightbox)

### Sharing

You can share your bot with other users so that multiple users can edit, manage, and collaborate on a bot. You can stop sharing with individual users anytime. You don't need to share a bot with another user for them to chat with the bot.

You can view the current access that a user has for your environment, and you have the option to assign security roles to the selected user.

> [!div class="mx-imgBorder"]
> [![Screenshot of Share your bot page with  message displayed in the Environment security roles section.](../media/share-your-bot.svg)](../media/share-your-bot.svg#lightbox)

**Bot author**, **Bot contributor**, and **Bot transcript viewer** are the three security roles for Microsoft Copilot Studio that you can manage at Microsoft Power Platform admin center.

You can assign the **Environment maker** security role when sharing a bot with a user who doesn't have sufficient environment permissions to run Microsoft Copilot Studio.

When you're sharing the bot, if the specified user doesn't have sufficient permissions to use Microsoft Copilot Studio in the environment, you'll be notified that the **Environment maker** security role will be assigned to the person so that they can use the bot.

The **Access** and **Authentication** options control who can access your bot. You can select one of two groups:

- **All bot managers** - This selection allows only bot managers to chat with the bot. You can share your bot so that other bot managers can access it.

- **Everyone in my organization (Organization name)** - This selection allows everyone in the organization to access and chat with your bot. Users who are outside of the organization will see an error when chatting with the bot.

The **Authentication** setting impacts how you can manage access to the bot.

Select **Manage** on the side navigation pane and then go to the **Security** tab and select **Authentication**.

> [!div class="mx-imgBorder"]
> [![Authentication dialog with the No authentication option selected.](../media/security-authentication.png)](../media/security-authentication.png#lightbox)

Three options for authentication are:

- **No authentication** - Any user who has a link to the bot (or can find it, for example, on your website) can chat with it. Therefore, the **Access** setting options will be disabled.

    > [!div class="mx-imgBorder"]
    > [![Access dialog showing the message "These controls are unavailable due to Authentication configuration."](../media/security-access.png)](../media/security-access.png#lightbox)

- **Only for Teams** - The bot will only work on the Teams channel, meaning that the user will always be signed in. Therefore, the **Require users to sign in** option in the **Access** setting will be enabled and can't be changed.

- **Manual (for any channel including Teams)** - This option has the following parameters:

  - If your authentication setting is configured to **Manual**, and the service provider is Microsoft Entra ID you can turn off the **Require users to sign in** option and change the access settings for the bot.

  - If your authentication provider is set as **Generic OAuth 2**, you can turn off the **Require users to sign in** option, but you can't control which users can access the bot. That option is only available when you use Microsoft Entra ID authentication.

### Web channel security

When you create a Microsoft Copilot Studio bot, it's immediately available in the Demo website and Custom website channels to anyone who knows the bot ID. These channels are available by default, and no configuration is needed.

Users can find the bot ID directly from within Microsoft Copilot Studio or by receiving it from someone. Depending on the bot's capability and sensitivity, that scenario might not be desirable.

With Direct Line-based security, you can enable access to only the locations that you control by enabling secured access with Direct Line secrets or tokens. You can enforce the use of secrets and tokens for each individual bot. After this option has been enabled, channels will need the client to authenticate their requests by using a secret or by using a token that is generated by using the secret, which is obtained at runtime. Any access to the bot that doesn't provide this security measure won't work.

On the side navigation pane, select **Manage > Security** and then select **Web channel security**.

> [!div class="mx-imgBorder"]
> [![Web channel security dialog box with Require secured access showing as Disabled.](../media/web-channel-security.png)](../media/web-channel-security.png#lightbox)

If you need to disable the **Web channel security** option, you can do so by switching **Require secured access** to **Disabled**. Disabling secured access can take up to two hours to propagate.

> [!div class="mx-imgBorder"]
> [![Enable require secured access dialog box showing "This action renders the Demo website unavailable, as well as any Direct Line channel not using a secret or token. This action can take up to two hours to take effect."](../media/enable-secured-access.png)](../media/enable-secured-access.png#lightbox)
