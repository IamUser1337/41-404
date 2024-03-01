
Customers are always looking for faster and more precise self-service support options, while businesses aim to satisfy their customers with faster, better customer service. One-way organizations are accomplishing this is with bots. A bot is a form of Artificial Intelligence (AI) that simulates human conversation through a chat interface. Bots listen for keywords and phrases that relate to the library of known, common customer issues (topics) that are stored in the bot, and it will return answers quickly and iteratively as the customer continues the chat. The bot continues to check if the customer's question has been answered, and then refines its selection of topics to solve the customer's problem. 

Power Virtual Agents empowers teams to easily create powerful chatbots using a guided, no-code graphical interface without the need for data scientists or developers. Bots created in Power Virtual Agents address many of the major issues with bot building in industry today. Power Virtual Agents eliminates the gap between the subject matter experts and the development teams building the bots, and the long latency between teams recognizing an issue and updating the bot to address it. It removes the complexity of exposing teams to the nuances of conversational AI and the need to write complex code. Also, it minimizes the IT effort required to deploy and maintain a custom conversational solution.

Check out this video for a brief overview of Power Virtual Agents: [**Engage customers with Microsoft's Power Virtual Agents**](https://youtu.be/J5i7h4Uzju4)

Using Power Virtual Agents will help your organization to:

- **Better empower your teams.** Your teams can build bots without needing intermediaries, coding, or AI expertise.

- **Reduce costs.** You can automate common inquiries, which will give agents time to focus on more complex issues.

- **Improve customer satisfaction.** Customers have access to an all day, self-help solution to help resolve their issues through comprehensive, personalized bot conversations.

:::image type="content" source="../media/describe-complementary-power-platform-solutions-02.png" alt-text="Diagram that shows the benefits of using Power Virtual Agents.":::

## Let’s look at some highlights of Power Virtual Agents:

- **Get started in seconds:** Power Virtual Agents is a software-as-a-service (SaaS) offering. It allows you to easily sign-up, create your chatbot, and embed it into your website with just a few clicks. There is no infrastructure to maintain or complex systems to deploy.

- **Empower your subject matter experts**: Using Power Virtual Agents, you are in the driver's seat. Your Subject Matter Experts (SME) can create chatbots quickly and easily using a novel, intuitive, code-free graphical interface**,** eliminating the need for AI expertise or teams of developers.

- **Enable rich, natural conversations:** Microsoft’s powerful conversational AI capabilities enable your end users to have rich multi-turn conversations that quickly guide them to the right solution. And, unlike most products on the market, there is no need to retrain AI models. Simply provide a few short examples of the topic you want the chatbot to manage, build the conversation using the graphical editor, and your chatbot is ready to manage customer requests. You can even try out your changes in real-time in the test pane.

- **Enable chatbots to act:** Chatbots that can chat with your users are great, but chatbots that can act on their behalf are even better. With Power Virtual Agents, you can easily integrate with services and back-end systems out-of-the-box, or through hundreds of easy-to-add custom connectors using Power Automate. This makes it simple to create a chatbot that not only responds to the user, but also acts on their behalf.

- **Monitor and improve chatbot performance:** Power Virtual Agents lets you keep an eye on how your chatbots are performing using powerful metrics and AI-driven dashboards. Easily see which topics are doing well and where the chatbot can improve, and quickly make adjustments to improve performance.

The image shows an example of the analytics available from a bot such as the number of sessions the bot had, resolution rate, and engagement. 


:::image type="content" source="../media/describe-complementary-power-platform-solutions-03.png" alt-text="Screenshot of the Analytics page." lightbox="../media/describe-complementary-power-platform-solutions-03.png":::
  

## **Components of Power Virtual Agents**

When you create chatbots with Power Virtual Agents, you author and edit topics. Topics are discrete conversation paths that, when used together within a single chatbot, allow for users to have a conversation with a chatbot that feels natural and flows appropriately. Creating a chatbot with Power Virtual Agents is easy to do with the no-code authoring canvas, and there are many ways you can manage how topics interact, how you want the conversation to flow, and what it should feel like. It is also easy to test the chatbot without having to fully deploy the chatbot whenever you make a small change. There are also lesson topics that guide you through topic authoring, from simple to complex scenarios, as well as default system topics. You can also choose what language you want your chatbot to use.

### **Topics**

In Power Virtual Agents, a topic defines how a chatbot conversation plays out. You can author topics by customizing provided templates, create new topics from scratch, or get suggestions from existing help sites.

A topic has trigger phrases, which are phrases, keywords, or questions that a user is likely to type that is related to a specific issue. Topics also have conversation nodes, which are what you use to define how a chatbot should respond and what it should do.

The AI uses natural language understanding to parse what a customer type and find the most appropriate trigger phrase or node. For example, a user might type "Open hours" into your chatbot. The AI will be able to match that to the **Store hours** topic and begin a conversation that asks which store the customer is interested in, and then display the hours the store is open.

You can see how the chatbot conversation works in practice by testing it in the **Test chatbot** pane. This lets you fine-tune the topic until you are ready to deploy it without having to exit the Power Virtual Agents portal.

### **Entities**

A big part of chatbot conversations in Power Virtual Agents is natural language understanding, which is the ability for the AI to understand a user's intent. For example, natural language understanding is involved when a user might say "I tried to use my gift card, but it doesn't work" and the chatbot is able to route the user to the topic related to gift cards not working, even if that exact phrase is not listed as a trigger phrase.

One fundamental aspect of natural language understanding is to identify entities in a user dialog. An entity can be viewed as an information unit that represents a certain type of a real-world subject, like a phone number, zip code, city, or even a person's name.

### **Actions**

You can enable your chatbot to perform an action by calling a Microsoft Power Automate flow. Flows can help you automate activities or call backend systems. For example, you can use flows with end-user authentication to retrieve information about a user after they sign in.

You can call flows from within topics, as a discrete **Call an action** node. You can utilize flows that have already been created in your Power Apps environment, or you can create a flow from within the Power Virtual Agents authoring canvas.

### **Publishing**

With Power Virtual Agents, you can publish chatbots to engage with your customers on multiple platforms or channels. These include live websites, mobile apps, and messaging platforms like Microsoft Teams and Facebook. After you have published at least once, you can connect your chatbot to additional channels.

Each time you want to update your chatbot, you publish it again from within the Power Virtual Agents app itself. This will update the chatbot across all the channels where you've inserted or connected your chatbot. You can also configure a Power Virtual Agents chatbot to provide authentication capabilities, so users can sign in with any OAuth2 identity provider, such as Azure Active Directory (Azure AD), a Microsoft account, or Facebook.
