When you create copilots with Copilot Studio, you author and edit topics. Topics are discrete conversation paths that allow users to have a conversation with a copilot that feels natural and flows appropriately. Those copilot conversations do need to be within a single copilot. Creating a copilot with Copilot Studio is easy to do with the no-code authoring canvas. There are multiple ways you can manage how topics interact, how you want the conversation to flow, and what it should feel like. It's also easy to test the copilot without having to fully deploy the copilot whenever you make a minor change. There are also lesson topics that guide you through topic authoring, from simple to complex scenarios, and default system topics. You can also choose what language you want your copilot to use.

### Topics

In Copilot Studio, a topic defines how a copilot conversation plays out. You can author topics by customizing provided templates, create new topics from scratch, or get suggestions from existing help sites.

A topic has trigger phrases, which are phrases, keywords, or questions that a user is likely to type that are related to a specific issue. Topics also have conversation nodes, which are what you use to define how a copilot should respond and what it should do.

The AI uses natural language understanding to parse what a customer type and find the most appropriate trigger phrase or node. For example, a user might type "Open hours" into your copilot. The AI is able to match that to the **Store hours** topic and begin a conversation that asks which store the customer is interested in, and then display the hours the store is open.

You can see how the copilot conversation works in practice by evaluating it in the **Test copilot** pane. This preview lets you fine-tune the topic until you're ready to deploy it without having to exit the Copilot Studio portal.

### Entities

A significant part of copilot conversations in Copilot Studio is natural language understanding, which is the ability for the AI to understand a user's intent. For example, natural language understanding is involved when a user might say "I tried to use my gift card, but it doesn't work." The copilot is able to route the user to the topic related to gift cards not working, even if that exact phrase isn't listed as a trigger phrase.

One fundamental aspect of natural language understanding is to identify entities in a user dialog. An entity can be viewed as an information unit that represents a certain type of a real-world subject, like a phone number, zip code, city, or even a person's name.

### Actions

You can enable your copilot to perform an action by calling a Microsoft Power Automate flow. Flows can help you automate activities or call backend systems. For example, you can use flows with end-user authentication to retrieve information about a user after they sign in.

You can call flows from within topics, as a discrete **Call an action** node. You can utilize flows that were already in your Power Apps environment, or you can create a flow from within the Copilot Studio authoring canvas.

### Publishing

With Copilot Studio, you can publish copilots to engage with your customers on multiple platforms or channels. These include live websites, mobile apps, and messaging platforms like Microsoft Teams and Facebook. After you published at least once, you can connect your copilot to more channels.

Each time you want to update your copilot, you publish it again from within the Copilot Studio app itself. This process updates the copilot across all the channels where you inserted or connected to your copilot. You can also configure a Copilot Studio copilot to provide authentication capabilities, so users can sign in with any OAuth2 identity provider, such as Microsoft Entra ID, a Microsoft account, or Facebook.