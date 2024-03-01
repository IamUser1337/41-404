
Do you find yourself regularly downloading email attachments and then uploading the file to the database? Every business in every industry has repetitive tasks that impact their organization. The process of getting a new purchase order approved might involve taking a form from your desk to get it approved. An employee might need to log into a website every morning to find daily numbers and then save those numbers into another system. Not only can repetitive processes like these be time consuming, but they can also be prone to errors. If someone mis-enters something, it could result in a missed deadline or a financial loss.

Microsoft Power Automate is about having computers manage repetitive tasks. It gives anyone with the knowledge of the business process to create a repeatable flow that when triggered, leaps into action and performs the process.

Common scenarios and capabilities of Power Automate:

- Automating repetitive tasks such as moving data from one system to another. 

- Guiding a user through a process so they can complete the different stages. For example, a sales organization might want to guide sellers through the process of selling products to customers. 

- Automating desktop based and website processes with Robotic Process Automation (RPA) capabilities. For example, a user working at a bank needs to update the exchange rates daily. The user would use RPA to log in to the website and retrieve the exchange rates. They would then save these rates to their desktop and update them in a company spreadsheet. 

Power Automate works by creating flows. These flows are then used to do things such as interact with different systems, guide users through a process, or make users more productive by automating daily tasks. 

## Types of flows

There are three primary types of Power Automate flows:

- **Business process flows**: These flows are used in model-driven apps to help people get work done. They provide a streamlined user experience that leads people through the processes their organization defined for interactions that need to be advanced to a conclusion of some kind. 

- **Cloud flows**: These are the most commonly used flows. Cloud flows begin with a trigger such as receiving an email from a specific person, or a mention of your company in social media. Once triggered, they also generally include one or more actions such as creating a record in a different system or sending an approval request to someone.

- **Desktop flows** - These robotic process automation (RPA) flows allow you to record yourself performing actions on your desktop or within a web browser. You can then trigger a flow to perform that process for you. You can also pass data in or get data out of the process, letting you automate even "manual" business processes.


### Business process flows

Business process flows are mostly used in model-driven applications to help users get work done. They typically represent a process that a user follows through to completion. They provide a streamlined user experience to provide them with the best way to advance to a conclusion of some kind. 

Some common scenarios where organizations might use business process flows are: 

- **Sales Process:** Organizations can create sales focused business process flows that guide sellers through the entire sales process ensuring that they are following the organization proven sales procedures for maximizing their chance of winning the deal. 

- **Case Resolution:** Support centers might create service centered business process flows that guide agents through the process of creating a case, troubleshooting the case, and ultimately resolving the case. 

- **Event Planning:** An event planning company might use a business process flows to ensure that they are not missing a step when they are planning an event. Stages in the process can exist for booking the venue, planning the meal, defining entertainment details and more. 

- **Selling a home:** A real estate company might use a business process flow to assist their agents in getting a home ready for an open house. This might include having stages for capturing inspection details, staging the property, and coordinating with staff to ensure someone is available at the time. 


In the image, we see an example of a business process flow used to help guide an agent through the process of fielding an offer from a potential buyer. 

:::image type="content" source="../media/04-describe-automation-power-automate-01.png" alt-text="Screenshot of a sample business process flow.":::

During each stage, there's information that needs to be logged. Based on the information captured, the stages of the business process flow might change. For example, since the **Counter Offer** field is set to yes, the counter offer stage appears. If the **Counter Offer** field was set to no, the stage wouldn't appear. 
 
### Cloud flows

As stated, cloud flows are the most common Power Automate flows. Cloud flows use connectors to interact with different services. Currently there are over 1,000 prebuilt connectors available. These connectors allow you to interact with data from other Microsoft products and data from non-Microsoft vendors such as Google, Salesforce, Oracle, and more. 

There are three main types of cloud flows that you can create: 

- **Automated flows:** These flows are automatically triggered by an event. This might be the arrival of an email from a specific person, or a mention of your company in social media. These are the most used cloud flow. 

- **Instant flows:** These flows are started automatically and are done with the click of a button. You can automate for repetitive tasks from your Desktop or Mobile devices. For example, you might use an instant flow to instantly send a reminder to the team with the push of a button from your mobile device.

- **Scheduled:** These flows run on a defined schedule. They might be used to fire off daily data uploads to Microsoft SharePoint or a database.

Now that we explored the types of cloud flows you can create, let’s explore some common scenarios where organizations might use cloud flows.

- **Approvals:** They can be used to automate approval processes such as invoice approval, time off requests, project approval, and more. 

- **Application integration:** They can be used to allow an application to interact with another application. For example, a technician in the field might use a dedicated app to request a part. A Power Automate flow could automatically order the part in the company’s inventory system. 

- **Improve productivity:** End users might create personal Power Automate flows to automatically do things such as saving attachments received via email to specific locations like SharePoint or OneDrive.

More advanced examples of organizations utilizing Power Automate flows might include:

- Interfacing with a custom Application Programming Interface (API) built by a financial services company to automatically retrieve the most recent loan rates, and then calculate the rate of an individual based on their credit score. 

- Create a smart data filing system whereas documents are received, and the content in them are scanned. Based on the type of document it is automatically filed in a specific location and could even be flagged as needed. 

Since there are hundreds of templates available to support different scenarios, cloud flows are easily created by anyone. 
 
### Desktop flows

Desktop flows are used to simulate user interaction with an application or a website. Desktop flows are often referred to as RPA. Think of it as a computer playing back tasks and steps that are otherwise done by an individual. In Power Automate, these types of flows are built using Power Automate for desktop. Desktop flows are different than cloud flows. A cloud flow performs an action based on API calls, whereas a desktop flow is like a macro as it's playing back previously recorded steps in order. 

Some of the common scenarios where an organization might use desktop flows are: 

- **Improve employee productivity:** A desktop flow can be created to replicate the actions of an end user who performs repetitive tasks. An example would be interacting with a specific website such as an interest rate site, and then entering that information into another application like an Excel Spreadsheet.

- **Interacting with a legacy system:** Many organizations are still using home built legacy applications that don't have modern APIs available that could be used by a cloud flow. In these instances, you can still automate the interaction with the legacy application without needing to rebuild the application from the ground up. 

- **Automating website interaction:** Many users need to interact with specific websites daily to enter details or capture information. For security reasons, many companies don't provide access to their APIs to allow you to do direct automation with their platform. A Desktop flow is a great way to mimic the user interaction and provide an automated solution. 

- **Automate working with terminal emulation software:** Many organizations use terminal emulation software such as Citrix to reduce hardware cost. Users log into simulated desktops. Many of these users perform repetitive tasks. Desktop flows can be used to mimic user keystrokes and automate activity. 

There are just some of the many different examples where an organization could use desktop flows. Let’s look at another example. In this example, a real estate company uses a website to see if new properties have any environmental items attached to the property. If any are found, they take a screenshot of the report and log it into Excel. In this video, we show you how a desktop flow could automate this process after a new property is entered into their property management model-driven application. 

[**Desktop flow**](https://www.microsoft.com/videoplayer/embed/RW10CDX)

## Business scenario

Often, a desktop flow is part of a bigger overall automation solution. For example, an event management company provides different package tiers to their clients to help them with cost savings on their event. This means that clients don't need to pay separately for each service. The event management company pays the vendors on behalf of the client. For example, when they plan a wedding, they book the venue, hire the caterer, book the entertainment, and even sometimes hire a florist. When the event is complete, each vendor sends them an invoice for the services they provided.

That process is as follows:

- Vendor invoices are received as email attachments in a dedicated email box. 

- Invoice attachments are downloaded from the email and scanned to determine what the invoice is for. Details such as the vendor, invoice date, and invoice amount are extracted from the attachment. 

- Invoices are sent to a specific person to be evaluated and either approved or denied, based on the services provided. 

- Individuals receive and interact with this request in Teams. 

- Invoice is approved and a new invoice is created in the event management companies legacy invoice application. 

- Invoice number is generated once the invoice has been entered. A confirmation email that the invoice was processed is sent back to the vendor. This includes the invoice number. 

The image shows a high-level breakdown of what this automation would look like in a Power Automate flow.

:::image type="content" source="../media/04-describe-automation-power-automate-02.png" alt-text="Diagram that shows the automation flow for the process described.":::


The whole process is done with a cloud flow. 

1. The cloud flow is triggered automatically when an email is received in the dedicated mailbox in Outlook.

2. AI Builder is used to extract details from the invoice attachment such as the vendor, invoice date, and amount.

3. An approval request is sent to the appropriate person in Microsoft Teams. The request includes the invoice details extracted from it.

4. Once the approval request is complete, a condition evaluates if the invoice was approved or rejected. 

5. Based on the approval status:

	- **Approved:** If approved, the cloud flow runs a desktop flow that was created to interact with the legacy application. The invoice details such as the vendor, invoice date, and amount are used in the creation of the invoice record.

		- Once the invoice is logged, the invoice number is captured, and a new email is created in Outlook. The email includes the status of the invoice and the invoice number.

    -  **Rejected:** if the invoice is rejected, the cloud flow creates a new email in Outlook, letting the vendor know their invoice wasn't approved. 
