Organizations always search for ways to provide better service to their customers and improve overall customer satisfaction. One way to accomplish this task is through conversational bots. Bots can help reduce the load on live agents by allowing incoming conversations on different channels to be routed to a bot first. Bots can assist the customer by going through basic troubleshooting. If needed, the bot can escalate the conversation to a live agent who could further assist the customer in their journey.

Microsoft Copilot Studio allows you to create powerful AI-powered chatbots to assist with a range of requests, from providing simple answers to common questions, to resolving issues that require complex conversations. With Microsoft Copilot Studio, organizations can create bots without the need for data scientists or developers, helping to reduce the time that it takes to deploy a bot solution. A Microsoft Copilot Studio bot contains multiple topics. Consider a topic as a way of representing a question or an item that the bot can assist with.

A topic contains two primary components:

- **Trigger** - Represents keys words and phrases that a user can enter that help the system identify which topic to use.

- **Conversation path** - A series of messages, actions, and other items that guide the customer through the topic.

For example, an organization might create a topic that's related to returning items. When a customer asks how to return an item, the system will recognize the text in the trigger. Then, it will use the conversation path that's associated with that topic to provide guidance to the user and help them with their issue.

The text that the user provides is compared against the different trigger phrases for all topics that are defined in the bot to find the most relevant topic. While a trigger phrase doesn't need to exactly match what the user entered, the system still needs to compare what the user provided against all triggers to find the correct topic. Based on the complexity of your bot, you might create hundreds of different topics. Creating hundreds of topics can be time-consuming, and it can be challenging when important information is present but isn't identified in a trigger. For example, personal identifying information, such as a phone number and addresses, might be needed to help identify the correct customer record in other systems that your organization uses. To handle these types of scenarios, organizations can integrate other services into a Microsoft Copilot Studio bot.

One cloud-based service that can help with this task is Microsoft Azure AI Services for Language. It can be used in Microsoft Copilot Studio bots to provide necessary tools to take your bots to the next level. This module will describe how to use Azure AI Services for Language in your Microsoft Copilot Studio bots.

Before you learn about the specifics, you'll first learn about Azure AI Services for Language.
