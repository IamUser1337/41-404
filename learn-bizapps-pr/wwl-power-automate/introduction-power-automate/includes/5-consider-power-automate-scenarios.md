
Most organizations utilize multiple applications and services every day. Users are sending and receiving emails in one application, while salespeople and service reps might be working in the organization’s Customer Relationship Management (CRM) system. Having so many different applications, it's common to have processes or procedures that need to pass information across these applications. 

One of the advantages of Power Automate is how easily it works with the different applications that organizations use each day. This is true even when the applications aren't built from the same vendor. For example, using connectors, you can easily trigger a flow when an order is created in Salesforce and store a copy of it in SharePoint. Regardless of which services and applications an organization is using, there are many times when a flow interacts with many of the most popular Microsoft technologies. A flow can be triggered when someone creates a new document in Microsoft SharePoint or sends an approvals card to a manager in Microsoft Teams. Power Automate can easily be used to create processes around interact with those applications. 

Let’s examine some use-cases related to popular Microsoft technologies. 

### Use flows with approvals

We mentioned approvals a few times throughout this module. Whether you need written acknowledgment from a manager or a formal authorization from a diverse group of stakeholders, getting things approved is part of almost every organization.

With the approvals capability in Power Automate, you can automate approval requests and combine human decision making into workflows. When you submit an approval in a flow, approvers are notified and can review and act on the request.

Some popular cases where approvals can be used include:

- **Approving vacation time requests:** Employees can submit a vacation request via a dedicated application, or by filling out a vacation request form. The request is sent to a manager who can approve or deny the request. 

- **Approving documents that need sign off:** Documents that require approval or signing off can be easily sent to the appropriate person to be signed off on. Once approved, a confirmation or copy of the signed document could be sent to all parties to confirm it was completed. 

- **Approving expense reports:** After an employee fills out an expense report, a Power Automate flow can identify the person’s manager, and send them the report for their approval. 

For more information about using approvals in Power Automate, see: [Get started with approvals.](/power-automate/get-started-approvals)
 
### Power Automate and Microsoft SharePoint

Microsoft SharePoint is a popular application that allows organizations to create sites where users can share documents and information with colleagues, partners, and customers. With the document management capabilities of SharePoint, users can easily track different versions of documents, and collaborate with others. With SharePoint being used to support so many different scenarios, it makes sense that organizations would want to be able to automate many of the different elements. 

Let’s look at some different examples of how you can use Power Automate with SharePoint:

#### Managing approval flows 

There are multiple ways that Power Automate could be used to support approval processes in SharePoint. For example, documents that contain sensitive information such as personal details, financial details, or strategies often require approval. With the content approval feature in SharePoint, you can put an approval process for documents in a specific document library. Any documents pending approval aren't visible to users until they're approved. This approach prevents documents that don't meet organizational standards accidentally being used which could result in financial losses. 

Another example is related to SharePoint sites. Organizations often create SharePoint team sites that connect team members with shared content and resources. When users create pages on a site, organizations can start an approval process to ensure the content aligns with organizational standards. SharePoint can be easily configured to require that changes to a site be approved before they go live. 

#### Working with files and lists

There are many scenarios where Power Automate flows can be used with SharePoint files and lists. One example is using Power Automate flows to help manage permissions of an individual item in a list or a file that is stored in a document library. For example, a flow could be used to grant access or provide approval for when an item is created or added to a specific folder. When an item is created, an approval request is created. Once the request is received, the flow sends the request to a manager who could approve the request. 

:::image type="content" source="../media/describe-building-automation-with-power-automate-08.svg" alt-text="Screenshot of template for processing approvals on SharePoint list items.":::

Additionally, Power Automate flows could be used to create SharePoint items based on actions occurring in other applications, such as an invoice being created in an Enterprise Resource Planning application. For example, one an invoice is created, the Power Automate flow could save the invoice as a PDF, and then save the file to a dedicated customer folder in a SharePoint document library. 

For more information about using SharePoint and Power Automate together, see: [Use SharePoint and Power Automate to build workflows.](/power-automate/sharepoint-overview) 
 
### Using Power Automate with Microsoft Outlook

Microsoft Outlook is the most widely used email application in businesses. Users not only use it for sending and receiving email, but they also use it for managing their individual contacts and managing their daily activities. This provides many different opportunities where Power Automate could potentially be used to automate Outlook scenarios. For example, a real estate agent might create and store customer contracts in popular document services such as Dropbox, OneDrive, or SharePoint. Once a customer contract is created, a Power Automate flow could automatically create an email to the customer and attach the newly created contracts as attachments. Additionally, once the customer sends back the signed contract, another flow could save the signed contracts back to the document repository. This helps the real estate agent ensure that contracts are being sent out and cataloged in a timely manner, and there are no manual steps the agent needs to take. 

:::image type="content" source="../media/04-describe-automation-power-automate-09.png" alt-text="Screenshot of list of Outlook flows." lightbox="../media/04-describe-automation-power-automate-09.png":::


In most organizations, two popular connectors are used for email flows regularly: the [Outlook.com](/connectors/outlook/) for personal email scenarios and the [Office 365 Outlook](/connectors/office365/) connector for business scenarios. Both connectors offer similar operations that you can use to manage your mail, calendars, and contacts. You can perform actions such as send mail, schedule meetings, add contacts, and more with either of these connectors.

For more information about using Outlook and Power Automate together, see: [Using Outlook and Power Automate](/power-automate/email-overview)

### Using flows with Microsoft Forms

Microsoft Forms is an online tool for creating surveys and polls. It’s useful for gathering customer feedback, assessing employee satisfaction, and organizing team events. There are many instances where forms or polls created with Microsoft Forms could benefit from automation. For example, schools frequently use Microsoft Forms for student quizzes. A teacher could use a flow that notifies them when a student turns in a quiz. A real-estate organization might use Microsoft Forms for new clients to provide details about themselves and the types of properties they're interested in. With a Power Automate flow, after a potential client completes the form, an email notification could be sent to an agent in their area. This ensures that the agent reaching out to the customer is local and ensures that the agent can engage with the customer as soon as possible. 

Various templates are available to help flow creators build flows for different Microsoft Forms scenarios. These include initiating an approval process based on form submissions or tracking Microsoft Forms responses in Microsoft Excel.

In the image, we filtered the list to only display templates that work with Microsoft Forms. We were able to take it one step further and search for templates that work with Outlook. The list of templates shows only templates that include Microsoft Forms and Outlook. 

:::image type="content" source="../media/04-describe-automation-power-automate-10.png" alt-text="Screenshot of list of Forms flows." lightbox="../media/04-describe-automation-power-automate-10.png":::


For more information about using Microsoft Forms and Power Automate together, see: [Overview of flows with Microsoft Forms](/power-automate/forms/overview)


## Using flows with Microsoft Teams

Microsoft Teams is a robust messaging and collaboration tool used globally by organizations. It provides employees with a workspace for real-time collaboration, meetings, and sharing files and applications.

Power Automate flows can be used in three scenarios with Teams:

- **Trigger** flows from Teams messages: In this scenario, you can create flows that are triggered when someone selects a Teams message. The flow can then run like any other flow you create. For more information, see: [Flows from Teams messages](/power-automate/trigger-flow-teams-message).

- **Use flows with** adaptive cards: Here, adaptive cards can be used as the trigger for flows. A full set of rich adaptive cards is available to you. For more information, see: [Adaptive cards.](/power-automate/create-adaptive-cards)

- **Create flows from within the** Power Apps app in Teams: Use the Power Apps app in Teams to create flows that use Dataverse for Teams. Dataverse for Teams is a built-in, low-code data platform for Teams that empowers users to build custom apps and workflows within Teams by using Power Apps and Power Automate. For more information, see: [Power Apps in Teams](/power-automate/teams/create-flows-power-apps-app), and [Dataverse for Teams](/power-apps/teams/overview-data-platform).