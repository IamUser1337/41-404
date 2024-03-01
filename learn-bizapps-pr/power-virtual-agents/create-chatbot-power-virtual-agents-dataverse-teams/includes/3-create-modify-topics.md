The Microsoft Copilot Studio defines copilot conversations by *topics*. With topics, you can define and control the way that the conversation evolves. 

Two types of topics are:

- **Trigger phrases** - The copilot needs to detect when the user asks a question that it knows how to respond to. The trigger phases are the phrases, keywords, and questions that the user is likely to enter. We recommend that you have 5 to 10 trigger phrases of common ways that your users would request help on the topic.

- **Conversation nodes** - When the copilot has a question, it needs to know how to handle the request. Conversation nodes define how the copilot responds and if actions are required.

To view and edit topics in your copilot, select **Topics** from the left column in the Microsoft Copilot Studio editor. Many topics are automatically created for a copilot:

- The first four topics are sample **user topics** that demonstrate various ways of using topics to create conversations.

- The remaining topics are **system topics** that are likely needed during a copilot conversation.

## Change the greeting system topic

System topics improve the usability of your copilot with prebuilt topics to handle greeting, escalating, starting over, and saying goodbye. Editing these topics allows you to further personalize the copilot for your users and organization.

The **Greeting** system topic provides a welcome message for the user. It's important to clearly define what the copilot is meant to do, which will set expectations with the user.

1. Select the **Greeting** system topic to go to the authoring canvas.  Notice that your authoring canvas includes a **Trigger Phrases** node and several **Message** nodes.

    The authoring canvas is where you design the topic's conversation path by using *conversation nodes*. Conversation nodes determine how a copilot responds and what actions it might have to take. See the following table for the different types of conversation nodes that you can add.

	|     Conversation   node    |     Description                                                           |
	|----------------------------|---------------------------------------------------------------------------|
	|     Ask a   question       |     Have the   copilot ask a question and get a response from the user    |
	|     Add a   condition      |     Add branching   logic                                                 |
	|     Call an   action       |     Call Power   Automate flows or Authenticate                                          |
	|     Redirect to another topic | Take the user to another topic in the copilot |
	|     Show a   message       |     Have the   copilot respond to the user                                |
	|     End with   survey      |     When the   conversation ends, a survey appears                        |
	
	All copilots start with the trigger phrases and a message conversation node.

1. If the text in the first message node doesn't match the purpose of your copilot, you can change it. You can use the text editing controls in the message node to have the questions appear in italic font, or you can paste italic text into the message node since the node supports rich text.  Change the text to the following example.

    Hi! I'm the virtual agent for the Sales Project Team. For our upcoming sales events, I can help find the event contact for a particular country/region. Just type in questions like *Who are the event contacts?* or *I need event contacts.* to get started.

1. Save the changes by selecting **Save** from the top right of the ribbon. Copilot Studio provides an on-screen notification when it has saved your changes.

1. Exit the topic authoring canvas by selecting **Back** from the top left of the ribbon.

## Create a topic

For the **Event Contacts** copilot, you want the copilot to respond to the question, "Who are the event contacts?" From the **Topics** page in Microsoft Copilot Studio in Teams:

1. Select **+ New topic** > **From blank**.

1. To name this topic or add details about it, select **Details** from the ribbon at the top of the screen.  Name your topic **Event Contacts**.

1. Select the **Trigger Phrases** node and add/enter the following phrases.

    `who are the event contacts`

    `event contacts`

    `who to contact for the event`

    `event contact information`

    `event info`

1. In the **Message** node just below the **Trigger Phrases** node, enter the following information. Use the editing options in the text box to apply bold formatting to the country/region names. Remember that the node supports rich text formatting, so you can copy/paste bold text into it.

    The event team contacts for North America are:

    **USA**
	Lynne Robbins `LynneR@contoso.com`

	**Canada**
	Lidia Holloway `Lidia@contoso.com`

1. Select the plus **+** symbol under the **Message** node to add another conversation node.

1. Select **Redirect to another topic > End of Conversation**.  You can enter “end” in the Search pane to filter the list or scroll to find it.

    The **End of Conversation** option is a system topic on how to end the conversation. This system topic asks the user about the accuracy of the results and to rate their experience.

1. Now, save your copilot by selecting the **Save** button from the right side of the **Copilot Studio** ribbon.

	You can view the **End of Conversation** topic by selecting the **View topic** link in your **End** node.

	Remember, you can edit any of the system topics by selecting them from the **Topics** list.

1. The **Test copilot** panel is open by default on the left side of your edit canvas. If you don't see it, you can select the **Test copilot** button from the right side of the command ribbon. In the **Test copilot** panel, enter questions that contain one of your trigger phrases to observe how the copilot responds.

1. Since Copilot is working for you, it can adapt other inputs as well. Try entering these phrases to see how it reacts (you can reset the test copilot in between tries):

	`contacts for the event`

	`contacts`

	Did you notice that Copilot provided the event team contacts with both prompts?

Congratulations, you've created your first copilot by using Microsoft Copilot Studio for Teams. The next unit expands the copilot to use inputs, variables, and conditions.
