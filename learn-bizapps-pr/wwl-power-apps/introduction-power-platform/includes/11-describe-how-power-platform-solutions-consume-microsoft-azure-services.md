The Azure cloud platform consists of hundreds of products and cloud services designed to help you bring new solutions to life to solve today's and future challenges. These services range from data storage services to virtual machines, to artificial intelligence services. Microsoft Azure service provides you with the opportunity to build, run, and manage applications across multiple clouds, on-premises, and at the edge, with the tools and frameworks of your choice.

Power Platform and Azure services are a perfect complement for each other, and the possibilities for using them together are endless. Azure services can be used with Power Platform to help modernize legacy systems, automate processes, and create advanced analytical solutions. 

Let’s look at an example of how an organization might use Azure and Power Platform.

The example demonstrates how you can deploy portals to automate manual or paper-based processes and create a rich user experience. Employ Azure API management and Azure Functions to connect custom APIs, which tap into your legacy systems. By using Azure-managed databases and a low-code approach to automate tasks, you can lower the overall solution costs. You can quickly build apps that are real-time, resilient, and scalable.

 
:::image type="content" source="../media/01-describe-bv-pp-07.png" alt-text="Diagram of Power Platform-based airline application using Azure Services.":::

The data flows through the solution as follows:

1. The airline system communicates with a custom API hosted in [Azure API Management](/azure/api-management).

2. A custom API coordinator receives notifications and handles incoming messages from the airline system, assigning flights to Microsoft Teams channels and sending them to [Power Apps](/power-apps).

3. The system queues a Graph API call in an Azure Storage Account queue for further processing when a user selects a flight to monitor, or when the system assigns the user to a flight

4. [Azure Functions](/azure/azure-functions) runs the Graph API calls based on the incoming messages in the storage queue, sending notifications to Teams, and also streams all events to an [Azure Event Hubs](/azure/event-hubs/) for further analytics.

5. The airline's notification system uses a custom bot messaging service that employs [Azure Bot Service](/azure/bot-service).

6. Custom bots send flight updates to users in Teams.

7. An [Azure Data Lake](/azure/storage/blobs/data-lake-storage-introduction) storage offers long-term retention and micro-batch processing of events from Event Hubs, ultimately generating insightful reports with Power BI.
