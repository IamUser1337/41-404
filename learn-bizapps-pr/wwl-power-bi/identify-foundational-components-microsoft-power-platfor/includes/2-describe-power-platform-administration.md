
## Power Platform environments

In Power Platform, environments are used to store, manage, and share your organization's business data, apps, and flows. Each environment allows you to provision one Microsoft Dataverse database for use within that environment. Microsoft Dataverse environments allow you to manage user access, security settings, and the storage that is associated with that database.

Each environment is created under a Microsoft Azure Active Directory (Azure AD) tenant. Only users within that tenant can access its resources. An environment is also bound to a geographic location, like the United States. When you create a Microsoft Dataverse database in an environment, that database is created within datacenters in that geographic location. Any items that you create in that environment (including connections, gateways, flows that are using Power Automate, and more) are also bound to their environment's location. 

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-01.png" alt-text="Illustration of production, test, and development environments for three different datacenters based on location.":::

You can create more than one environment to manage solution development and data storage by setting up one environment for development, another for testing, and another for production use. The development environment is for developers to create solutions. Once the solutions are ready for testing, they're moved to another environment called test. A separate environment ensures that everything can be tested without impacting users. Once the solution is ready, it can be moved to production. Also, you can set up an environment based on a geographical location. For example, you might set up an environment for Europe and another for Asia. Each of these environments has zero or only one instance of Microsoft Dataverse.

## Administrative experiences

Microsoft Power Platform has a rich set of administrative experiences that can be used to administer the different aspects of your solution. From the Power Platform admin center, you can create new environments or manage security. From the maker portals you can manage Microsoft Dataverse. Depending on what you want to do, there's a targeted administrative experience for it. Let’s examine the many different experiences available. 

### Microsoft Power Platform admin center

The Power Platform admin center (Https://admin.powerplatform.microsoft.com) is the primary administrative experience for the Microsoft Power Platform. The portal allows administrators to manage their environments and configure many of the primary settings for Power Apps, Power Automate, and customer engagement apps for Dynamics 365.

In the Power Platform admin center, settings are grouped into broad categories and are accessed by selecting the link on the left-hand side of the portal. These categories are:

- **Home:** Provides overall information, such as if there are any services disruptions, etc. Different cards can be added to better personalize this screen based on your needs. 

- **Environments**: This section lists all the environments in this tenant. This includes Microsoft Dataverse environments and other environments such as Dataverse for Teams environments. 

- **Analytics:** This section provides analytical details about Microsoft Power Platform such as Dataverse analytics, Power Automate Flow Statistics, and Power Apps details. 

- **Billing:** The billing center contains details related to user licenses. 

- **Settings:** This section lets you review and manage settings at a tenet level, such as being able to control who can create and manage the different types of environments available. 

- **Resources:** This section is where you can view capacity statistics for your tenant and manage and install features related to Dynamics 365 applications. 

- **Help + Support:** This section is where you can create new support requests and manage any existing requests previously submitted. 

- **Data integration:** This section lets you create or add predefined connections and monitor these connections between Microsoft Dataverse and other data stores like Salesforce or SQL Server.

- **Data:** This section is where you can manage the different data sources, on-premises data gateways, and virtual network data gateways associated with this tenant. 

- **Policies:** This section is where you can manage some of the different data security policies and other security features, such as the Customer Lockbox and tenant isolation. 

- **Admin Centers:** Provides access to the different admin centers that can impact Microsoft Power Platform solutions such as the Microsoft 365 admin center, Azure active directory, and more. 

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-02.png" alt-text="Screenshot of Power Platform admin center.":::

### Other admin and maker portals

In addition to the Power Platform admin center, there are several different administrative experiences that can be used as part of Power Platform. Each experience is designed based on the product you're working with. For example, the primary experience used to make applications and manage the Dataverse instance associated with an environment is the Power Apps maker portal ([Https://make.powerapps.com](https://make.powerapps.com/)). 

In the image, you can see an example of the maker portal displaying the different model and canvas applications that are currently deployed to this environment. 

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-03.png" alt-text="Screenshot of maker portal.":::

The Power Apps maker portal also provides for the following items: 

- **Tables:** Allows you to manage the Microsoft Dataverse tables deployed in this environment. You can easily create new tables and perform tasks such as modifying the different forms, views, and relationships in the Dataverse instance. 

- **Connections:** Allows you to manage the connections being used by apps in this environment. 

- **Flows:** Provides access to any flows created for this environment. 

- **Chatbots:** Provides access to any chatbots created for this environment.

- **AI Models:** Provides access to AI builder models for this environment.

- **Solutions:** Provides access to any Solutions deployed to this environment.

- **Cards:** Provides access to Cards created in this environment.

- **Choices:** Allows you to manage the choice columns in this environment. 

- **Connections:** Allows you to manage the connectors used in this environment.

- **Dataflows:** Provides access to Dataflows used in this environment.

- **Power Platform:** Provides access to other Power Platform Maker portals.

Items in the middle section can be pinned and displayed as needed. For example, if your organization isn't doing anything with Cards, you can choose to not display the middle section. If you access it, you can select more items, which are then displayed displayed. 

Each of the primary Power Platform components has a corresponding maker portal. The table provides a list of the different maker portals available.

| **Product**| **URL**| **Description** |
| - |
| **Power Automate**| [https://make.powerautomate.com](https://make.powerautomate.com/)| Used to create and manage the Cloud and Desktop flows deployed. |
| **Power BI**| [https://app.powerbi.com](https://app.powerbi.com/)| Used to create and manage Power BI reports and dashboards. |
| **Power Pages**| [https://make.powerpages.microsoft.com](https://make.powerpages.microsoft.com/)| Used to create modern, secure business websites that can be used by employees and customers. |
| **Microsoft Copilot Studio** (formerly Power Virtual Agents)|[https://web.powerva.microsoft.com](https://web.powerva.microsoft.com/)| Used to create intelligent copilots that can be used by employees and customers. |


### Explore the different portals

Now that we'e talked about the different administrative experiences available, let’s see how to work with them. In the following video, we walk through some of the basic elements in the Power Platform admin center and introduce some of the other maker portals available. 

[**Power Platform admin center**](https://www.microsoft.com/videoplayer/embed/RW10pPX)

## Managed Environments

Managing applications at an enterprise level can be challenging. It can be hard to control who has access to different applications and ensure the data in those applications is secure. To help resolve this challenge, Microsoft Power Platform includes Managed Environments. Managed Environments is a suite of premium level capabilities admins can use to manage Power Platform at scale. They provide more control over the environment with less effort, and more insights related to what is happening. Any Power Platform environment can be a Managed Environment. Once the administrator enables the Managed Environment, other features become available that administrators can configure. These features cover different elements across Power Platform. 

Key features available in a Managed Environment include: 

- **Limit sharing:** Allows administrators to limit how broadly users can share canvas apps. For example, you can prevent a user from sharing a canvas app with the entire organization. 

- **Weekly usage insights:** Every week analytics are delivered to your mailbox. These analytics include information about your top apps, your most impactful makers, and details about inactive resources that you can safely clean up. 

- **Data policies:** Data policies define the consumer connectors that data can be shared with. They ensure data is managed in a uniform manner across your organization. Additionally, they also prevent important business data from being accidentally published to connectors like social media sites. 

- **Pipelines in Power Platform:** Power Platform administrators can create one or more pipelines, associate any number of environments, then share access with those individuals that administers or run pipelines.

- **Solution checker:** Solution checker in Managed Environments is used to enforce rich static analysis checks on your solutions against a set of best practice rules and identify problematic patterns.

The items mentioned represent a small portion of what Managed Environments provides. Increased capabilities are being added regularly. You can find the most recent list of Managed Environment capabilities here: [Managed Environments overview. ](/power-platform/admin/managed-environment-overview) 
