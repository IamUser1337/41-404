Before the solution architect creates datasets in Power BI, they should understand the data and requirements in relation to Power BI capabilities.

## Location of the data

Reporting highly depends on the data structure and volumes, in addition to user expectations. The solution architect should ask the following questions about the data that is required for reporting:

- Is all data coming from Dataverse?
- Is reference data available that might be useful?
- What is the volume of data?
- How frequently does data need to be refreshed?
- How is the data related?
- What are the key fields that are needed to relate data?
- What are the key fields that contain analytics?
- How sparse are key data fields?
- What data can be left behind?

> [!IMPORTANT]
> The size of data and refresh frequency can impact licensing.

## Who consumes the output

The solution architect needs to understand the requirements about who looks at Power BI reports and dashboards, and then they should ask the following questions:

- Who consumes the Power BI visualizations?
- Are data security considerations available regarding use of data?
- Do people use the Q&A feature?
- Are plans in place for using alerts?
- Are plans in place for using mobile?
- Do external stakeholders exist?
- Are licensing considerations necessary?

## Required security

Solution architects should understand what sets of data that each user is permitted to see in Power BI. A key consideration is whether the data shown in Power BI should be the same as the data seen through the provided apps. Or whether the solution architect should be able to see more summarized data.

Other security considerations:

- Power BI content in shared model-driven app dashboards must also be shared in Power BI.
- Shared dashboards are refreshed in context of the report owner, not the user who is viewing the dashboard.
- Determine whether row-level security (RLS) needs to be configured or not.
- Assess if you should exclude or obfuscate secure fields and personal data.
- Examine aggregating data in the query.
- Limit the export data options in Power BI.

> [!IMPORTANT]
> Power BI and Dataverse have no synchronization privileges. Consequently, you could inadvertently grant other people access to confidential data in Power BI.

Consider the frequent scenario where:

- The user should only have access to their own data.
- Managers should only have access to their own team's data.
- Executives should have access to all data.
- Data has been imported into a dataset and combined with data from other systems.

To meet these requirements, you need to limit access to rows based on assigned roles in the dataset by using RLS.
