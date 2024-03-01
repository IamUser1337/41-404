Data modeling is a science, and data modeling professionals and established standards for data modeling do exist. To be effective with Dataverse data modeling, you don't have to be a professional data modeler or use special tools. Popular tools like Microsoft Visio can be used to quickly create a basic entity relationship diagram (ERD) that visualizes the relationships and flow of data between tables. 

This unit focuses on general best practices for data modeling for Dataverse deployments, including: 

- Data models should be updated continuously during a deployment. Frequently, a data model is designed at the beginning of a project, but it's important that the design process doesn't stop at that point. As you go through the deployment, new columns and tables will be added. You need to capture these new columns and tables in the data model and then make it a living data model. Additionally, you should recommend to customers that they continue to update the data model as they enhance the system.

- Use established tools to help you start. Community tools are available with the [XrmToolBox](https://www.xrmtoolbox.com) that help make it easier for you to quickly generate ERD diagrams of your Dataverse configuration. These tools include the UML Diagram Generator and the Entity Relation Diagram Creator. After you complete configuration updates, you can generate an up-to-date ERD diagram.

- Don't include every table. Some core tables, such as Activities, Notes, and Users (record owners) are related to nearly every table in Dataverse. If you include every relationship with these tables in your data model, the result will be unreadable. The best practice is to only include the primary tables that are used in your configuration in your data model diagram and only include custom relationships with the User and Activity tables to maximize readability.

- Data models should include tables outside of Dataverse. If you're integrating with other systems by using Dataverse data connectors or virtual tables, or if you're integrating with data flows outside of Dataverse by using an integration, this data should also be represented in your data model diagram.

- Start simple with the standard tables and then add custom table relationships to your data model.

- Experience should influence your data model. Occasionally, it can be easy to over-normalize your data, but in the process, you can make the application more cumbersome to use.

Start with what you need now, but design the data model in a way that will support what you will be doing in the future. For example, if you know that you'll eventually need to store more details about sales territories, you can use a text column for territory now, which will make it more difficult to implement than if you use the territory table relationship. Plan ahead for what is coming.

## Out-of-the-box vs. custom tables

This topic identifies standard, *out-of-the-box* tables that are used in the configuration, along with custom tables and the purpose for which they're being used. This information matters because Microsoft Dataverse has many common tables and, as a general rule, a custom table shouldn't be created if a standard table already exists that addresses that purpose. The reason is because, if you overload your configuration with many redundant tables, you'll negatively impact the performance of the system, and you'll make the system more difficult to use (having many redundant-sounding tables in **Advanced Find** will confuse users). Each custom table should serve a specific purpose. 

Additionally, this topic will help identify tables that are most used and identify if you are at risk of overloading tables.

### Reconsider replacing standard tables with custom tables

Occasionally, makers consider replacing standard functionality with custom tables. The reasoning behind that consideration is that if the makers need a sales opportunity but need a simpler form than the standard opportunity form, creating a custom table might be easier. However, you should consider what you might be giving up by using a custom table instead of a standard table. Using an out-of-the-box table ensures greater alignment with core platform features. Because more features are added regularly to standard tables, you can benefit from new features when they're released. For example, if you decided to replace the standard opportunity table with a custom opportunity table, you won't be able to use the Sales Insights Add-in for Microsoft Dynamics 365 Sales and other AI features.

### Don't re-create accounts and contacts

When deploying Microsoft Power Platform solutions, you'll frequently track multiple types of companies, organizations, and contacts in the system. Some of these entities represent customer/client organizations, while others might be support and advisory organizations, such as accountants and legal firms. Some entities might be miscellaneous types of organizations, such as trade associations.

The most common approach to managing multiple categories of company relationships is to use the Account table for all organization types and use a column, such as **Relationship type**, or a custom option set to flag companies by their type or category. You can filter views based on the type of company, and business rules can conditionally show or hide column and form components based on type.

To benefit from a standard integration with Dynamics 365 Finance and Operations apps by using the dual-write infrastructure, it's best to use the default tables and columns that are added by the dual-write core solution to your Dataverse environment.

Another approach is to create custom tables for each type of company. One reason that is commonly cited is, "I might need to use accounts for another reason in the future, so I don't want to customize the account table."

Before re-creating the Account table as a custom company table, you should strongly consider what you are giving up by creating a custom table. Consider the following factors:

- **Multiple addresses** - The Account table has a unique address capability that supports multiple addresses. The first two addresses are displayed on the company form, but these address records live in the related Customer Address table. While you can create a custom address table that is tied to a custom company table, re-creating the unique logic where the addresses are stored in the related table and are displayed on the form and table views would require development. If you need multiple addresses, use the Account table.
- **Contact hierarchy** - Accounts are the parents of contacts. Activities that are related to contacts will roll up to the parent account record. This hierarchy can't be replaced by a custom company record. You can create more relationships with custom company tables, but the standard account/contact relationship can't be replaced. If the company has contacts with their primary company relationships to this type of company, or if you want to roll up activities from contacts to companies, use the Account table.
- **Standard map control** - In model-driven apps, standard map control doesn't support custom company tables.
- **Hierarchical relationships** - Hierarchical relationships between parent/child accounts and the standard hierarchy visualization and roll-up of child account activities to the parent account only work with standard account tables.
- **Polymorphic lookup columns** - Dataverse includes a special type of polymorphic lookup column called a customer column. This column allows a row to be linked to a company/account or a contact. 
- **Marketing will not work** - Marketing lists can only work with contacts, accounts, and leads, not custom tables. Microsoft Dynamics 365 Customer Insights - Journeys can send to accounts and contacts, but not custom company tables.

Therefore, in almost every situation, the Account table should be used for company records of all types, with the following exceptions:

- Minor types of companies that aren't relational and have minimal attributes. Consider a type of organization with no contacts, no address, and that only exists for lookup purposes.
- Unqualified or unverified companies that are imported from business cards or web forms that you don't want to pollute the Account table with. For these situations, you could use the Lead table.

### Repurpose system tables

Consider the scenario where you have a business requirement that is similar to opportunities, but it's not a true sales opportunity. In this situation, you might consider repurposing system tables or creating new tables.

The following sections explain factors that you should consider before repurposing system tables.

#### Consider the future

The future of Microsoft Power Platform is moving faster than ever before, so using tables in non-standard ways can cause problems if Microsoft makes changes to the table that you're using. Also, if you choose to repurpose a seldom-used system table, such as Contracts, Microsoft might elect to deprecate that table in the future. Custom tables aren't deprecated. Additionally, if you repurpose a system table, consider what you might do if you later need that entity for its intended purposes. Customers who have repurposed a case eventually needed case management and had to address it with custom tables because the standard case table was already used for different purposes.

#### Consider overhead

Many system tables have certain columns that can't be removed from the forms. For example, some columns on tables, like Opportunity case and Campaign, can't be removed from the form. While you can hide these columns, having several locked columns on the form can add overhead to your environment configuration.

#### Consider the user experience

If your use case is less than 50 percent in line with the standard table functionality, a custom table will typically give users a simpler user experience than scaling down a more complex system table. It's also possible to add business process flows to any table, including custom tables, which can make a custom table user experience as good as, or better than, repurposing a system table.

## Avoid common pitfalls

Common data modeling issues include:

- **Too many tables** - Likely, the tables are over-normalized.
- **Too many columns on a table** - Likely, a separate table should have been created.
- **Use the tools** - Quick view forms instead of repeating columns.
- **Avoid the Yes/No data type** - If more values might be added, or you need to store the values as Unknown.
- **Formatting pitfalls** - You're endlessly stuck with data type formatting.
- **Unused parts** - Avoid building parts of the data model that you don’t plan to use.

## Proof of concept

Dataverse simplifies your ability to create a trial environment, and it's quick to create tables and relationships. You can build proof of concepts to try out your data model and see what the user experience might be like.
