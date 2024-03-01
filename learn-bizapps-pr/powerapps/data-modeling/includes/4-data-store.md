This unit compares data stores for your apps.

## Location of the data

When designing your solution, you should consider the existing data sources for your solution.

### New data

If your app is creating data that doesn't already exist, such as in situations where the existing business process was done by using paper, we recommend that you store the data in Dataverse.

### Read/write from an existing system

Data that reads/writes from an existing system is a type of data where you need to retrieve the latest information from an existing database or system. In these cases, data needs to be requested at the time when you need it.

### Make a copy of existing data

In situations where original data should never be modified or overwritten, you can copy the data to another data store such as Dataverse. This approach ensures that the data in the original system won't be changed, yet your app can work with it. This scenario is common when you are working with data in accounting and revenue-related systems.

## Where to store data

Data modeling on Microsoft Power Platform should look at the whole data architecture picture and include a logical look at data from Dataverse, data lakes, and external sources by using connectors.

### Dataverse

Dataverse abstracts your apps from how data is stored. All data in Dataverse is accessed through REST APIs. Currently, the tables in Dataverse are relational tables. Dataverse stores its data in a mixture of stores and formats:

- Microsoft Azure SQL Database elastic pools
- Microsoft Azure Cosmos DB
- Microsoft Azure Storage
- Microsoft Azure Data Lake Storage in Common Data Model folders

### Existing data

Apps in Power Apps have three ways of using existing data:

- **Connector** - A connector allows the app to connect to various systems and sources, such as SharePoint, SQL Server, or Microsoft 365, and directly retrieve data from them or save data to them.
- **Dataflows** - Dataflows extract, transform, and load data from another system to Dataverse or Azure Data Lake Storage. Unlike a connector, it fetches data in a scheduled batch. Instead of retrieving the data as-is from the data source, you can use Microsoft Power Query Online to manipulate, cleanse, and transform data before you store it to the target storage.
- **Virtual tables** - A virtual table is a custom table in Dataverse that contains data from an external data source. Virtual tables appear in your app to users as regular table rows, but they contain data that is sourced from an external database, such as an Azure SQL database. Virtual tables are no longer read-only, and apps can create and write data to virtual tables.

### Choose where to store data

When choosing where to store data for your solution, consider the following recommendations:

- **Dataverse** - For transactional data that your apps will consume and manipulate.
- **Azure Data Lake** - For data from other systems, read-focused, and brought into a Common Data Model structure.
- **Connectors** - For leaving existing data where it is and accessing other services that make their data available.
