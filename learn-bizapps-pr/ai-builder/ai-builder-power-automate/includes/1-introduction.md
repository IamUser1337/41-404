AI Builder is a Microsoft Power Platform capability that provides AI models that are designed to optimize your business processes. AI Builder enables your business to use intelligence to automate processes and glean insights from your data in Power Apps and Power Automate. With AI Builder, you don't need coding or data science skills to access the power of AI. You can build custom models tailored to your needs, or choose a prebuilt model that is ready to use for many common business scenarios.

## AI Builder usage in Power Automate

Power Automate offers AI Builder actions that enable usage of all model types in flows. Adding AI Builder actions in your flow allows you to:

- Perform model inference by using outputs of upstream actions (email attachments received, SharePoint files dropped, created records in a Microsoft Dataverse table, and so on).

- Process model inference results in downstream actions (send by email, store in Dataverse records, message in Teams, and so on).

The following illustration shows a simple flow with three main stages:

1. Receive an email in Microsoft Outlook.

1. Detect sentiment of the email body by using the AI Builder sentiment analysis model.

1. Send an email notification with the sentiment detected in the email by using the **Overall text sentiment** output from the AI Builder model

![A screenshot of a social media post description automatically generated](../media/01-social-post-flow.jpg)