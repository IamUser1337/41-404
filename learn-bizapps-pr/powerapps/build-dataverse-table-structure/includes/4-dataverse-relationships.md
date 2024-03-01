Before we build the **AccidentTable**, let's touch on the different types of relationships. As previously mentioned, you need to build the following relationships between your custom tables:

- A one-to-many relationship from the location table (LocationTable) to your main accident table (AccidentTable)

- A one-to-many relationship from the type of accident table (TypeofAccidentTable) to your main accident table (AccidentTable)

- A many-to-many relationship from the employee table (EmployeeTable) to your main accident table (AccidentTable)

For a more comprehensive explanation, see [Table relationships overview](/power-apps/maker/data-platform/relationships-overview/?azure-portal=true).

The goal is for you to understand why the preceding relationships apply to your business case and that they're correctly associated.

In this business case, you know that each accident (being tracked in **AccidentTable**) can occur in a particular location (being tracked in **LocationTable**). Therefore, in this case, an accident can occur many times in a single location. Occasionally, it might be simpler to consider the **LocationTable** as the parent and the rows of the referencing table as the children, or the **AccidentTable**.

The same logic applies to the relationship between the **TypeofAccidentTable** and the **AccidentTable**. Many accidents can occur with one type of accident. The **TypeofAccident** is the parent and the rows in **AccidentTable** are the children. A many-to-one relationship is the *child* perspective of a one-to-many relationship. To create these relationships, create **Lookup** data type columns in the next exercise.

The relationship between the **EmployeeTable** and the **AccidentTable** is of the many-to-many relationship type. The reason is because one employee can be involved in many accidents and one accident record can involve more than one employee. The rows of many-to-many relationships are identical and reciprocal. Dataverse creates a third table that's not visible in the tables list to build the relationship. This table holds a one-to-many relationship with both related tables and stores the values to define the relationship. In many-to-many relationships, no explicit columns are being created; you can create the relationship by selecting the two tables that you want to create the relationship for.

In the next exercise, you'll learn how to create the relationships.
