Data is important when you are deploying Microsoft Power Platform solutions. Your users can't help customers when no data is in the system. Typically, when you are replacing another business application with a solution based on Microsoft Dataverse, some data is migrated into the new system during the deployment so that users can see relevant business data when they start using the application.

## Data migration approaches and tools

Multiple types of tools and approaches are available for you to use when migrating data to Microsoft Dataverse. The following list is not exhaustive, but it includes some of the most common options:

- **Get data from Excel** - In the maker portal, you can select the **Get data** option when viewing a table and then import data from a Microsoft Excel or a .csv file.
- **Legacy data import utility** - You can import data to tables from .csv, .xls, .xml, and zip files.
- **Microsoft Power Platform dataflows** - In the maker portal, you can select **Dataflows** under the **Data** menu and then configure an import from various cloud data sources. Data from these sources can be transformed prior to import by using Microsoft Power Query.
- **Extract, transform, and load (ETL)** - You can extract, transfer, and load (ETL) software such as Microsoft Azure Data Factory. Data Factory has a connector for Microsoft Dataverse.
- **Outsourced tools** - Use tools from other sources such as Kingswaysoft.
- **Custom applications** - Use custom applications that are developed by using the API.

## When to perform data migration

Make sure that you perform data migration multiple times during a project for the following reasons:

- Developers and functional consultants will require data when building apps.
- Users will require data for user acceptance testing (UAT).
- Testers will require data for integration and performance testing.
- Subject matter experts require data for data validation testing.

## Sample data

Data migration will depend on your ability to get data from the source system. Often, this process can be delayed, so it might be necessary for you to create sample data for use in early development and testing activities.

## Test data migration

Data validation is a critical part of assessing the successful completion of data migration. Two aspects of data validation testing are data quantity and data quality. Data quantity refers to the number of rows that were expected to be created in Dataverse, and data quality is the correctness of data values as defined by data mapping.

Data quantity might not be a one-to-one match of records between the source environment and the test environment, especially for transaction data because the data model design might be different in the target environment. As another example, some data quality issues are systemic with customer's data. If a company has many different customer records for the same organization and you are integrating with their financial system, you're limited in how much you can improve their data. The testing team needs to be aware of similar issues to be effective at implementing their testing plan.

Data, such as record ownership and the **Created On/By** and **Modified On/By** information, will likely differ. Likely, this factor will be affected by users who no longer exist and different ownership. For that reason, you can't do a straight table compare. However, testing should validate that this situation is being handled correctly and is mapped as expected.

The expectations for data quantity and quality should be clearly identified as part of the data migration strategy and testing strategy. Similarly, the data values might not show up as exactly the same value due to the difference in the new schema or due to applied transactional logic. Key business users must be engaged in this testing activity, especially for quality. Customers should also consider using a separate environment for testing data rather than mixing it with UAT testing because it risks UAT users modifying the migrated data. The number of runs must also be planned with an initial small subset and then a significant 70 to 80 percent of full volume to ensure the correctness of migrated data.

Data validation testing is important to ensure that the data migration is completed properly because it will have a significant impact on correct functioning and adoption of the application. It is vital to raise awareness of the importance of data quality that is imported into the production system.

The solution architect needs to identify if the customer is missing certain aspects of this critical activity and then confirm that the customer is planning to validate imported data before going live to ensure data quality.

Key questions to ask yourself during data validation testing:

- Have you identified the scope for data validation?
- Have you identified subject matter experts to perform data validation testing? Does this list include users and managers?
- Have you considered integration/migration with a smaller record set and performance testing?
- Have you determined the strategy, outcome, and schedule for data validation testing?
- Have you identified the number of runs and data volume for each testing cycle?
- Have you defined the criteria for validating data quality and data quantity?
- Have you maintained separate environments for data validation?
- Are key test users aware of the transition logic that is being applied during data migration?

## Prioritize data migration

Don't underestimate the amount of effort that is required for data migration.

Data migration planning should take place immediately after the project has started. Data migration might identify data elements and business processes that have not been captured in the requirements analysis. It is crucial that these omissions are raised with the customer so that decisions regarding what to do with this newly identified data can be taken without jeopardizing the project.
