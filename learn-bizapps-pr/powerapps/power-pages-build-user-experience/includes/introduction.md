Microsoft Power Pages is built on top of Microsoft Dataverse. Power Pages extends functionality to internal and external audiences, but this functionality must already be present in a custom Microsoft Power Apps application by using Dataverse or a Microsoft Dynamics 365 application. For example, if you don't have Microsoft Dynamics 365 Field Service installed, you can't install the Field Service website solution.

Conversely, if you have Microsoft Dynamics 365 Sales installed, you can set up case management functionality on your website without needing to use code. In other words, Power Pages *extends* Power Apps functionality to internal and external web audiences.

This architecture comes with a major benefit. All differentiating features of model-driven Power Apps are the features of **Power Pages** as well, including: 

- Centralized management
- Common Data Model 
- Roles and permissions 
- Forms and views 
- Business rules 
- Declarative workflows and actions
- Microsoft Power Automate flows
- Plug-in architecture 
- Integration with other services
- Dataverse extensibility 
- Audit

Power Pages delivers a complete content management system out of the box, with all content stored in Dataverse. As a result, you can edit content through the Power Pages design studio and directly by using the Portal Management app. Additionally, the Dataverse security model can help you provide more secure content.

## Fit-gap analysis

The following sections examine the various scenarios when Power Pages can be a good fit and others where it's unlikely to deliver the same value.

### When to consider Power Pages

Consider using Power Pages in scenarios where you want to complete the following tasks:

- Expose Dataverse in a simple, secure web interface. This scenario might include external users (such as customers and partners) or internal users who don't require full-featured apps from Power Apps.
- Provide access to simple community forums, a self-service knowledge base, and web forms for service requests, cases, or other Dataverse tables.
- Require a website to read, update, and create Dataverse rows in an out-of-the-box, ready-to-deploy manner.
- Support limited resources and budgets for large-scale web development, business-user, and no-code configuration requirements.
- Create website content that's accessible across all resolutions, devices, and browsers.
- Provide multilingual implementations to serve audiences of different languages or when you're required to provide multilingual services by law.
- Create and transact selected information from Dataverse to anonymous public access.
- Secure connection to Dataverse to key external stakeholders by using the built-in authentication or external authentication providers, such as Microsoft Azure Active Directory B2C, Facebook, Google, LinkedIn, and more.

### When to exercise caution

When deciding to use Power Pages, you should exercise caution when:

- Most of the data that you want to show on the web resides in an external (non-Dataverse) system.
- Heavy requirements are established around document management, indexing, and searching.
- Commerce requirements include processing a high volume of payments and maintaining an online store.
- The use cases are more appropriate for direct, model-driven, or canvas apps.

## Performance considerations

Power Pages websites do autoscale as they get more interaction. How much a website scales depends on how much Dataverse and Power Pages capacity is purchased and assigned to the environment that the website is placed in. When planning and building a website, you'll need to ensure that the implementation is done in a scalable manner by using best practices and tools, such as solution checker, app checker, website checker, and so on. It's also important to recognize when to exercise caution regarding Power Pages scalability. For example, allowing visitors to upload files without restricting file size or type might have a detrimental effect on the overall website performance.
