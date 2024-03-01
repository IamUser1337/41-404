Microsoft Sustainability Manager uses Microsoft Power Platform and Power BI for analytics. Therefore, customers or partners can use Microsoft Azure and Microsoft Power Platform to extend the core capabilities of Sustainability Manager. You can achieve this goal quickly by using custom industry vertical or horizontal solutions, such as new formulas or reports. This approach combines the power of a publicly available data model with your data calculation, visualization, and reporting capabilities. In addition, you can use collaboration and chat capabilities through Microsoft Teams. 

The Microsoft Sustainability Manager solution is extensible by the growing partner ecosystem. Partners can implement the following features:

- Rich and robust digital solutions to support reporting, governance, and emissions reduction initiatives with extra analytics, digital twins, and AI-driven automation. 

- Data connectors to automate data ingestion.

This extensibility translates to incredible opportunities for delivering solutions and services on top of Microsoft Sustainability Manager, thus extending the ecosystem to reporting providers, governance, and vertical partner opportunities.

## Recommended practices for extensibility 

Microsoft Sustainability Manager provides several extensibility options. However, you'll need to adhere to the following best practices: 

- You can perform the same extensibility across Sustainability Manager as you would in Microsoft Power Platform. 

    > [!NOTE]
    > Some features may require additional licensing. 

- You can't change pre-existing fields on activity data; however, you can create new fields to extend the existing tables. Additionally, Sustainability Manager strictly adheres to the Greenhouse Gas protocols, so you won't be able to add more Scope 1, 2, or 3 emission sources.
 
- During the emission calculations, values will be pulled from activity data, emission factor libraries, and greenhouse gas factor values. You can't change the emission calculation formulas beyond the configured values in the aforementioned tables. The formula that's used is discussed later in the **Exercise - Design emission calculations** unit.

- You can extend the out-of-the-box tables, or you can create new tables and later use those extensions in your emission calculations by using Power FX expressions. These extensions will give you more control over your emission calculations and will allow for more complex calculations to occur.

- You can create custom Power BI reports for your data, or you can export data from Sustainability Manager to other analytics systems like Tableau, Databricks, or Snowflake. Data will synchronize to Microsoft Azure Data Lake Storage every 30 minutes, and this timing isn't adjustable. 

- Automatic goal check-ins, when set up, will occur once every 24 hours. You can't change this frequency.
