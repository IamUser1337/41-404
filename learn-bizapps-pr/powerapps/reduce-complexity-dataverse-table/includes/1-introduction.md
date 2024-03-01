When data is modeled in Microsoft Dataverse, separate tables are used to represent distinct objects and concepts. Organizations can use more tables to help secure specific information, avoid data repetition, describe other properties, or make the reporting easier. As real-life objects are related to each other, the relationships are used in Dataverse to link rows from one table to another. Additionally, relationships can provide constraints and behaviors that apply when actions are performed on the records.

Essentially, Dataverse tables and relationships can work together to tell the story of your data. When building a good user experience in a canvas app from Microsoft Power Apps by using the tables and relationships, you would want to hide unnecessary complexities of the data model. To accomplish that task, your formulas and data usage must efficiently navigate the tables by using the relationships. This module will examine how to use the different types of relationships that Dataverse offers.

## Scenario: Contoso shared workspaces

This module will use a common business scenario to demonstrate how Dataverse relationships work with canvas apps. Contoso, like many companies, has multiple locations and allows employees to work from home. Occasionally, these employees need to come into the office and will need a desk to use during their visit. Previously, Contoso instructed employees to walk around the office location on arrival to find an available desk. The company has since discovered that this type of shared workspace system, sometimes referred to as *hot desking*, has created challenges for IT support and licensing. As a result, the company plans to build a solution that employees can use that will allow them to view the available desks and reserve one in advance. The team that is building the solution has identified the following tables as part of their Dataverse data model.

|     Table name      |     Description                                                                                                                                                                                                                              |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Location        |     This table will represent the individual buildings   and will contain columns such as the address and phone number. Each location will have a primary contact   person.                                                                               |
|     Desk            |     This table represents the actual desk that a person   can reserve.  Desks are located at a   specific location.                                                                                                                                |
|     Desk feature    |     Different desks have different features. For   example, some desks might have a speakerphone, and some might be enclosed in a   room.   A standard list   of desk features will be included, and each desk can have one or more of those features.    |
|     User            |     Users represent people who can reserve the   desk or be a primary contact for a location.                                                                                                                                                |
|     Reservation     |     This table represents the reservation for a person   to use a specific desk at a specific location in a specific timeslot.                                                                                                                 |

## Dataverse relationship types

When you create a relationship between tables, the relationship type defines the cardinality constraints of each side of the relationship. Dataverse supports one-to-many and many-to-many relationships.

### One-to-many relationships

The one-to-many relationship (which is also called 1:N or parent-child) includes a primary (parent) table, where you can associate an individual row with many related (child) table rows by using a lookup column in the related (child) table. The primary row is called the parent, and the related table rows are called child rows. You can associate a child row with only one parent row.

A one-to-many relationship is also referred to as a many-to-one (or N:1) relationship, where you will use the relationship starting at the child pointing to the parent. It is the same physical relationship definition but from a different angle. In a canvas app, if you are working with the child record and want to display a property from the parent, you would use the many-to-one relationship navigation property on the child row.

By default, a single table is used as the primary, and the lookup column always points to a row from that table. Dataverse also supports multi-table lookups (occasionally referred to as *polymorphic lookups*), which allow a lookup field to point to a row from one of the multiple tables, providing flexibility for more complex data models. For example, you can set up a multi-table lookup column by creating a column of data type Customer. Then, you can set the customer lookup value to point to a contact or to an account table row. On all activity tables (for example, email, task, and so on), the corresponding column can point to any table that is enabled for activity tracking. Additionally, you can use the [Multi-table lookup](/power-apps/developer/data-platform/webapi/multitable-lookup/?azure-portal=true) column type to set up a custom multi-table lookup column. When working with these multi-table lookup columns in Power Apps, you will use the **IsType** and **AsType** Microsoft Power Fx functions to determine the parent table and to use the data.

In the module's example data model, the following one-to-many relationships have been defined to support the scenario.

|     Primary table    |     Related table     |     Description                                |
|----------------------|-----------------------|------------------------------------------------|
|     Location         |     Desk              |     Each desk is located at a location.         |
|     User             |     Location          |     Each location has a primary contact.        |
|     User             |     Reservation       |     User whom the desk is reserved for.         |
|     Desk             |     Reservation       |     Each reservation is for a specific desk.    |

When setting up a one-to-many relationship, you can also set up the relationship behaviors. Behaviors determine what should happen when the primary table row is deleted, assigned, shared, unshared, or reparented. The default behavior is reference, which is set up to remove the link between the two tables when the primary table row is deleted. For example, the Location table has multiple desks and uses the default configuration, so if your canvas app deleted a location row, then by default, all associated desks would be orphaned. If the business requirement is to remove associated desk records when a location is deleted, then you can select the **ForAll** function, which will delete all associated desk records first. A better option is to set up the parental type of behavior for the relationship. This behavior type automatically deletes the associated records when the primary record is deleted. This approach ensures that you won't have orphaned desk records.

When you are building a canvas app and using related tables, knowing how the behaviors are set up for that relationship will ensure that you implement the correct logic.

## Many-to-many relationships

The many-to-many relationship (also called N:N) includes a special hidden table called a relationship table, occasionally referred to as an intersect table. This table will map how the many rows of one table can be related to the many rows of another table. Many-to-many relationships can track the association, but you can't modify the intersect table to add custom columns that describe the relationship.

In this module's example, **Desk** and **Desk Feature** would have a many-to-many relationship. The list of desk features would be shared by all desks, and each desk could have one or more associated features. Many-to-many relationships allow users to know that the desk has chairs but will not let you store how many chairs that each desk had.

The following video demonstrates how to create relationships between tables.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWOUXs]

After you have created all tables and relationships, the data model for the example scenario should resemble the following diagram.

> [!div class="mx-imgBorder"]
> [![Diagram of an example data model that shows relationships between tables.](../media/table-relationship.png)](../media/table-relationship.png#lightbox)

The rest of this module explores how to work with this data model from a canvas app.
