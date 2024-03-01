Microsoft Copilot Studio gives you the flexibility to create bots in different environments. An environment is a space to store, manage, and share your organization's business data. The bots that you create are stored in an environment. Apps and flows are also stored in environments. Environments might have different roles, security requirements, and target audiences, and each environment is created in a separate location.

When creating a bot, you can select from only the list of environments that you have access to.

> [!div class="mx-imgBorder"]
> [![Select your bot's environment from the list of environments that you have access to in supported data locations.](../media/select-environment.png)](../media/select-environment.png#lightbox)

To create a bot in an environment where you don't have access, you'll need to be a system administrator or contact the system administrator. Then, you will need to complete the following steps:

- Create a bot in the environment (this step will install the necessary Microsoft Copilot Studio solutions).

- Assign the security role of "bot author" to you in the environment.

To assign the security role of "bot author," Microsoft Power Platform admin must go to Microsoft Power Platform admin center, select the environment, and then select **Settings**.

> [!div class="mx-imgBorder"]
> [![Microsoft Power Platform admin center with the Environments tab selected and the Settings button selected.](../media/environment-pva-settings.png)](../media/environment-pva-settings.png#lightbox)

In **Users + permissions**, select **Security roles**.

> [!div class="mx-imgBorder"]
> [![Settings with the Users + permissions section expanded and Security roles highlighted in that section.](../media/security-roles.png)](../media/security-roles.png#lightbox)

Select **Bot Author**.

> [!div class="mx-imgBorder"]
> [![The list of Roles with Bot Author highlighted.](../media/select-bot-author.png)](../media/select-bot-author.png#lightbox)

Select **+ Add people**.

> [!div class="mx-imgBorder"]
> [![Microsoft Power Platform admin center open to Environments > Contoso (default) > Settings > Security roles > Bot Author with the Add People button highlighted.](../media/add-people.png)](../media/add-people.png#lightbox)

You can search for the person whom you are looking for, select the name, and then select **Add**.

> [!div class="mx-imgBorder"]
> [![Choose the people who should be added to the role.](../media/add-person.png)](../media/add-person.png#lightbox)

The upper part of the screen will show a successful notification ribbon and the name of the user.

> [!div class="mx-imgBorder"]
> [![Message showing "Successfully added 1 user and 0 teams to the Bot Author security role."](../media/sucess-add-user-security-role.png)](../media/sucess-add-user-security-role.png#lightbox)

You have now successfully given a user bot maker access in an environment.
