In the previous units, you learned about directly referencing data sources from Power Apps. The two types of data sources were Tabular and Action based. As a refresher, they are as follows:

**Tabular data** - A tabular data source is one that returns data in a
structured table format. Power Apps can directly read and display these
tables through galleries, forms, and other controls. Additionally, if
the data source supports it, Power Apps can create, edit, and delete data
from these data sources. Examples include Microsoft Dataverse, SharePoint, and
SQL Server.

You can recognize Tabular data by looking for green highlighted text that returns a data type of **Table**. Tabular data won't include a function.

> [!div class="mx-imgBorder"]
> ![Screenshot of gallery items property populated with 'My Table'.](../media/tabular-data.png)

**Action-based data** - An action-based data source is one that uses
functions to interact with the data source. These functions could be used to return a table of data or to make updates to the data, such as send an email, update permissions, or create a calendar event. Examples include Office 365 Users, Project Online, and Azure Blob
Storage.

You can recognize Action-based data by looking for functions that return records, tables, or values. This will often be in the **OnSelect** property of a control, but not always.

> [!div class="mx-imgBorder"]
> ![Screenshot of a button with Office365Users.MyProfile() as the OnSelect property.](../media/action-based-data.png)

Both of these data source types are commonly used to bring data and
more functionality to your app. Also, there's one type of special
connection with Power Apps, the connection to Power Automate.

**Power Automate** - A cloud-based service that makes it practical and simple for line-of-business users to build workflows that automate time-consuming business tasks and processes across applications and services. Power Automate is a part of Office 365, and if you have a Power Apps license, then you also have a Power Automate license, meaning you can integrate its functionality to extend your Office 365 apps with no extra cost.

Power Automate can be used to enhance the capabilities of your app using its built-in actions. For example, you can build complex approvals, add business logic, better integrate with external data sources, and create PDFs. Later in this module you'll learn more about Power Automate and how to integrate it with Power Apps.

In the next unit, you'll learn about action-based connectors by adding the Office 365 Users connector to your app to both retrieve and update information.
