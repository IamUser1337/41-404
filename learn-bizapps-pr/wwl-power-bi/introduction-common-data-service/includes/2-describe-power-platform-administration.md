
**Power Platform environments**

In Power Platform, environments are used to store, manage, and share your organization's business data, apps, and flows. Each environment allows you to provision one Microsoft Dataverse database for use within that environment. Microsoft Dataverse environments allow you to manage user access, security settings, and the storage that is associated with that database.

Each environment is created under a Microsoft Entra ID tenant. Its resources can only be accessed by users within that tenant. An environment is also bound to a geographic location, like the United States. When you create a Microsoft Dataverse database in an environment, that database is created within datacenters in that geographic location. Any items that you create in that environment (including connections, gateways, flows that are using Power Automate, and more) are also bound to their environment's location. 

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-01.png" alt-text="Illustration of production, test and development environments for three different datacenters based on location.":::

You can create more than one environment to manage solution development and data storage by setting up one environment for development, another for testing, and another for production use. The development environment is for developers to create solutions. Once the solutions are ready for testing, they are moved to another environment called test. A separate environment ensures that everything can be tested without impacting users. Once the solution is ready, it can be moved to production. Also, you can set up an environment based on a geographical location. For example, you might set up an environment for Europe and another for Asia. Each of these environments has zero or only one instance of Microsoft Dataverse.

  



**Administrative experiences** 

Microsoft Power Platform has a rich set of administrative experiences that can be used to administer the different aspects of your solution. From the Power Platform admin center, you can create new environments or manage security. From the maker portals you can manage Microsoft Dataverse. Depending on what you want to do, there's a targeted administrative experience for it. Let’s examine the many different experiences available. 

### **Microsoft Power Platform admin center**

The Power Platform admin center (Https://admin.powerplatform.microsoft.com) is the primary administrative experience for the Microsoft Power Platform. The portal allows administrators to manage their environments and configure many of the primary settings for Power Apps, Power Automate, and customer engagement apps for Dynamics 365.

In the Power Platform admin center, settings are grouped into broad categories and are accessed by selecting the link on the left-hand side of the portal. These categories are:

- **Home:** Provides overall information, such as if there are any services disruptions, etc. Different cards can be added to better personalize this screen based on your needs. 

- **Environments**: This section lists all the environments in this tenant. This includes Microsoft Dataverse environments and other environments such as Dataverse for Teams environments. 

- **Analytics:** This section provides analytical details about Microsoft Power Platform such as Dataverse analytics, Power Automate Flow Statistics, and Power Apps details. 

- **Billing:** The billing center contains details related to user licenses. 

- **Settings:** This section lets you review and manage settings at a tenet level, such as being able to control who can create and manage the different types of environments available. 

- **Resources:** This section is where you can view capacity statistics for your tenant and manage and install features related to Dynamics 365 applications. 

- **Help + Support:** This section is where you can create new support requests and manage any existing requests that have been previously submitted. 

- **Data integration:** This section lets you create or add predefined connections and monitor these connections between Microsoft Dataverse and other data stores like Salesforce or SQL Server.

- **Data:** This section is where you can manage the different data sources, on-premises data gateways, and virtual network data gateways associated with this tenant. 

- **Policies:** This section is where you can manage some of the different data security policies and other security features, such as the Customer Lockbox and tenant isolation. 

- **Admin Centers:** Provides access to the different admin centers that can impact Microsoft Power Platform solutions such as the Microsoft 365 admin center, Azure active directory and more. 

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-02.png" alt-text="Screenshot of Power Platform admin center.":::


### **Additional admin and maker portals**

In addition to the Power Platform admin center, there are several different administrative experiences that can be used as part of Power Platform. Each experience is designed based on the product you are working with. For example, the primary experience that is used to make applications and manage the Dataverse instance associated with an environment is the Power Apps maker portal ([Https://make.powerapps.com](https://make.powerapps.com/)). 

In the image, you can see an example of the maker portal displaying the different model and canvas applications that are currently deployed to this environment. 

:::image type="content" source="../media/identify-foundational-components-of-the-microsoft-power-platform-03.png" alt-text="Screenshot of maker portal.":::


The Power Apps maker portal also provides for the following items: 

- **Tables:** Allows you to manage the Microsoft Dataverse tables deployed in this environment. You can easily create new tables and perform tasks such as modifying the different forms, views, and relationships in the Dataverse instance. 

- **Connections:** Allows you to manage the connections being used by apps in this environment. 

- **Flows:** Provides access to any flows that have been created for this environment. 

- **Chatbots:** Provides access to any chatbots that have been created for this environment.

- **AI Models:** Provides access to AI builder models for this environment.

- **Solutions:** Provides access to any Solutions that have been deployed to this environment.

- **Cards:** Provides access to Cards created in this environment.

- **Choices:** Allows you to manage the choice columns in this environment. 

- **Connections:** Allows you to manage the connectors that are being used in this environment.

- **Dataflows:** Provides access to Dataflows being used in this environment.

- **Power Platform:** Provides access to other Power Platform Maker portals.

Items in the middle section can be pinned and displayed as needed. For example, if your organization isn't doing anything with Cards, you can choose to not have it displayed. If you access it, you can select more, which are then displayed displayed. 

Each of the primary Power Platform components has a corresponding maker portal. The table provides a list of the different maker portals available:

| **Product**| **URL**| **Description** |
| - |
| **Power Automate**| [https://make.powerautomate.com](https://make.powerautomate.com/)| Used to create and manage the Cloud and Desktop flows deployed. |
| **Power BI**| [https://app.powerbi.com](https://app.powerbi.com/)| Used to create and manage Power BI reports and dashboards. |
| **Power Virtual Agents**| [https://web.powerva.microsoft.com](https://web.powerva.microsoft.com/)| Used to create intelligent chatbots that can be used by employees and customers. |
| **Power Pages**| [https://powerpages.microsoft.com](https://powerpages.microsoft.com/)| Used to create modern, secure business websites that can be used by employees and customers. |


 

**Explore the different portals**

Now that we'e talked about the different administrative experiences available, let’s see how to work with them. In the following video, we walk through some of the basic elements in the Power Platform admin center and introduce some of the other maker portals available. 

[**Power Platform admin center**](https://www.microsoft.com/videoplayer/embed/RW10pPX)
