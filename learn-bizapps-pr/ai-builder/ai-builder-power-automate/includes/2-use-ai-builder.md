This section describes various use cases that can be fulfilled by using AI Builder and Power Automate.

## Prerequisites

- Access to [Power Automate](https://flow.microsoft.com/?azure-portal=true)

- A license or trial of the [AI Builder](/ai-builder/administer-licensing)

- An [environment](/power-platform/admin/environments-overview) with a [Microsoft Dataverse database](/power-platform/admin/create-database). (Applicable only for work or school accounts)

- A basic understanding of Power Automate and experience with creating a flow is recommended.

## Invoice processing

Businesses often handle a high volume of invoices received through various channels like mail, email, fax, and in-person submissions. Manually inputting this data into your database is a time-consuming task. However, there are more efficient ways to manage this process:

1. Utilize **AI Builder's document processing model** to automatically extract relevant information, including columns and tables, from your invoices.

1. Implement a Power Automate flow to seamlessly transfer this extracted data into your database.

These automated steps significantly reduce the manual workload, improve accuracy, and enhance productivity in your invoice processing workflow.

## Analyze email sentiment

Employees might want to manage their emails based on the emotions conveyed in the content. For instance:

- If your boss seems upset, you'd like to understand why right away.

- If a customer expresses dissatisfaction, a swift response can prevent further frustration.

- After sharing a document, you'd want to track both positive and negative feedback.

AI Builder comes to the rescue by analyzing the overall sentiment of a text, even breaking it down by sentence. With a Power Automate flow, you can automatically apply **AI Builder's sentiment analysis model** when you receive an email. This way, you'll be promptly notified about the emotional tone of important emails.

Furthermore, you can enhance this sentiment analysis by using **AI Builder's key phrase extraction model** to identify key topics or phrases within the emails.

## Dematerialize documents

Certain companies maintain multiple physical sites where important information is collected on paper. Later, an agent must painstakingly transcribe this paper-based data into a central system.

Here's how you can enhance this process using Power Automate and AI Builder:

1. Agents can snap a picture of each paper audit record and store it in a designated folder.

1. A Power Automate flow takes over, processing all new images in the folder. It employs the **AI Builder text recognition model** to extract information from these forms, and then securely stores this data in the central tool.

A similar approach can be applied to efficiently digitize business cards in bulk using the **AI Builder business card reader model**. This combination of technology streamlines data capture and reduces manual data entry, saving time and minimizing errors.

## Filter support requests by language
In customer support, teams often receive requests from customers all over the world. The challenge is that different teams handle requests in various languages. Therefore, it's crucial to identify the language of incoming requests swiftly to ensure they're directed to the right teams.

To address this scenario, you can create a Power Automate flow that:

1. Analyzes the language of an incoming email using the **AI Builder language detection model**.

1. Routes the email to the appropriate team's mailbox based on the detected language.

This solution streamlines the process, ensuring that customer requests are directed to the right team from the get-go, improving efficiency and customer service.

## Categorize feedback

In the world of customer feedback, a company that's out in the public eye might receive a mix of comments covering various aspects, like check-in, rooms, staff, or restaurant quality. To make sense of it all, here's what they can do:

1. **Gather New Feedback**

   - **Power Automate collects data:** It can pull in fresh feedback from different sources, such as new Twitter messages mentioning the company's name or from a centralized data repository like a table in Microsoft Dataverse. The flow is triggered when, for instance, a new tweet appears or a new record is added.

1. **Sort the Feedback Using AI Builder**

   - **AI Builder category classification model:** This clever tool takes the gathered feedback and categorizes it. So, it automatically figures out if a comment is about check-in, rooms, staff, or the restaurant, making it easier to organize and address.

This setup helps a company stay on top of the feedback they receive, ensuring that they can respond more effectively and improve their services. It's like having a smart assistant for customer comments!

That's it for this unit! Now that you know more about how Power Automate and AI can assist with streamlining various business processes you're ready to build a custom flow using AI connectors. Head to the next unit, **Exercise - Use AI Builder actions in Power Automate** to continue on your learning path.