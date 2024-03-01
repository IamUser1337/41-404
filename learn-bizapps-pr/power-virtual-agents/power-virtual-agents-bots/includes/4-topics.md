Now that the initial structure of the copilot has been created, your next step is to begin writing topics. Topics define how the customers interact with the copilot, and they typically represent common issues, questions, or tasks that customers might need assistance with. For example, you might create a topic to provide customers with item return instructions.

Each topic consists of two primary elements:

- **Trigger phrases** - Phrases, keywords, or questions that are entered by users and relate to a specific issue.

- **Conversation nodes** - Define how a copilot should respond and what it should do.

You can design topics by [customizing provided templates](/power-virtual-agents/authoring-template-topics/?azure-portal=true), creating a new one, or using a topic that has been suggested from existing sites. Your copilot can have up to 1,000 topics.

## Get started with topics

Each created copilot includes several predefined topics to help you get started. These predefined topics are separated into two types:

- **Lesson** - Precreated user topics that can help you understand simple and complex ways of using nodes to create copilot conversations.

- **System** - Prepopulated topics that represent common use cases that can occur during a copilot conversation.

## Work with lesson topics

The intent of lesson topics is to provide examples of how to use topics to solve specific scenarios and to help you become more comfortable as you create copilots. Lesson topics range from simple, such as providing a user with store hours, to more complex scenarios, where the copilot assists online shoppers with items in their cart.

The following table describes the four included lesson topics.

| Topic | Description | Notes |
|-------|-------------|-------|
| Lesson 1 – A simple topic | Goes through the creation of a simple topic with one conditional branch that displays store hours. | |
| Lesson 2 – Simple topic with condition and variable | A simple topic that contains one conditional branch and a variable that displays store locations based on the customer's preferred store location. | A variable is a name for an item that is used later in the topic flow. In this example, pva_StoreLocation is the variable that is used to store the user's response when you ask for their preferred store location. |
| Lesson 3 – Topic with conditions, variables, and a prebuilt entity | Goes through the creation of a topic that includes one conditional branch, a variable, and an entity. In this lesson, the copilot uses the State entity and recognizes any US state that the user enters. | Topic entities help identify key information from what the user enters and automatically fills in that information into your variables. For example, if you type "I want to buy a red car," the copilot doesn't need to ask which color because the copilot recognizes the Color entity in the content that you typed. The copilot then skips the question that asks for color. |

## System Topics

System Topics represent scenarios that customers are likely to encounter while interacting with your copilot. These scenarios might include initiating and ending a conversation or escalating a conversation to a live agent. System topics have a basic structure already in place, based on what the scenario is. For example, the greeting topic already has predefined triggers and a basic conversation path that you can begin to modify based on your needs.

> [!div class="mx-imgBorder"]
> [![Screenshot of the system tab showing triggers and statuses.](../media/system-topics.png)](../media/system-topics.png#lightbox)

## Create topics

You define any other topics by selecting **Topics** in the side navigation pane and then selecting **Add** at the top of the page. There are two options for
creating topics:

- **From blank:** Opens a new blank topic. You create everything from the triggers to conversation flow, etc.

- **Create from description:** Uses Copilot to assist you in creating your topic. You provide some basic details about what you want and the topic is created.

Each topic that you define should include some trigger phrases. Trigger phrases are examples of text such as questions or utterances that teach the copilot when to respond with this dialog. For example, the following image contains a topic called Store Hours, which is used to provide customers with store location hours based on different scenarios.

> [!div class="mx-imgBorder"]
> [![Screenshot of creating topics process on navigation pane.](../media/store-hours.png)](../media/store-hours.png#lightbox)

Six trigger phrases have been added, such as *What are your hours?* and *When are you open?* These phrases are used to determine when the Store Hours topic should be initiated. The more trigger phrases you add, the more likely it is that the topic is appropriately used. Trigger phrases should be unique to each topic. If you have the same trigger in multiple topics, the copilot can't identify which topic to load. After you have added the initial triggers, select **Save topic** to add the topic to the **Topics** list. More triggers can be added later as needed.

Once you have defined your trigger phrases, you can define how customers are guided through their conversational interaction with the topic. The authoring canvas is a graphical dialog tree editor that allows you to define copilot responses and the overall copilot conversation.

> [!div class="mx-imgBorder"]
> [![Screenshot of the trigger with phrases captioned Trigger phrases will be pre-populated based on what you defined on the previous screen.](../media/authoring-canvas.png)](../media/authoring-canvas.png#lightbox)

## Work with conversation nodes

Conversation nodes help define the path that the conversation takes. Conversation nodes can display messages, ask questions, or run actions. You can add these nodes by selecting the plus sign (**+**) below the node. For example, if you want to provide store hours based on where the customer lives, you would add an **Ask a question** node to identify which store location they want the hours for.

The following image shows the **Ask a question** node being used to ask the customer, which store location they want the hours for. In addition, the customers are provided with two multiple-choice options to choose from: Seattle and Bellevue.

> [!div class="mx-imgBorder"]
> [![Screenshot of the question node with caption Different node types can be inserted based on what you want to display or capture, and the Options node with caption Options are presented as buttons in the chat conversation window.](../media/question-node.png)](../media/question-node.png#lightbox)

Separate conversation paths are created based on the customer's response. In the forked conversation path, each node has automatically checked for **Seattle** in one path and **Bellevue** in the other path to take the appropriate next step. More nodes can be added for each path based on what you want it to do.

The following image shows that for each path, a **Message** node is added that provides the store hours for that specific location.

> [!div class="mx-imgBorder"]
> [![Screenshot of the message node on each path with store hours.](../media/branching.png)](../media/branching.png#lightbox)

You now have a simple branching dialog tree and can create more complex versions of this tree. You can incorporate [variables](/power-virtual-agents/authoring-variables/?azure-portal=true), [entities](/power-virtual-agents/advanced-entities-slot-filling/?azure-portal=true), and [Power Automate flows](/power-virtual-agents/advanced-flow/?azure-portal=true).
