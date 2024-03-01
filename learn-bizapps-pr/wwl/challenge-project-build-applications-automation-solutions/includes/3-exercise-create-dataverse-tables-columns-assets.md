

Northwind Traders need the following data model configured.  In this exercise you will:
- Create tables and columns for players and scouting reports.
- Create relationships for contacts, players, scouts (Users), and scouting reports.
- Create needed forms and views.
- Add new column to the contact table.

## Specification
Create the data model as detailed.

### Player table columns
| **Column**               | **Type**                                                                      | **Requirement** |
|--------------------------|-------------------------------------------------------------------------------|-----------------|
| First name               | Single line of text                                                           | Required        |
| Last name                | Single line of text                                                           | Required        |
| Height                   | Single line of text                                                           | Required        |
| Weight                   | Single line of text                                                           | Required        |
| Date of birth            | Date only                                                                     | Optional        |
| Position                 | Single line of text                                                           | Optional        |
| Experience               | Single line of text                                                           | Optional        |
| Salary                   | Currency                                                                      | Optional        |
| Contract expiration date | Date only                                                                     | Optional        |
| Last drug test           | Date only                                                                     | Optional        |
| Drug test result         | Choice: Unknown, Passed, Failed, Inconclusive. Make Unknown the default value | Optional        |
| Minutes per game         | Decimal                                                                       | Optional        |
| Points per game          | Decimal                                                                       | Optional        |
| Filed goal percentage    | Decimal                                                                       | Optional        |
| Free throw percentage    | Decimal                                                                       | Optional        |
| Three-point percentage   | Decimal                                                                       | Optional        |
| Primary scout            | Lookup to the user table                                                      | Optional        |
| Photo                    | Image file. Use this as primary image                                         | Optional        |
| Full name                | Single line of text: Calculated from first and last name                      |                 |
| Age                      | Whole number: Calculated from Date of birth                                   |                 |

### Other requirements for the Player table
Player status can be Active, Recruiting, Draft Prospect, Free Agent, and Retired.

### Scouting report table columns

| **Column**     | **Type**                              | **Requirement** |
|----------------|---------------------------------------|-----------------|
| Name           | Single line of text                   | Required        |
| Player         | Lookup to the player table            | Required        |
| Strengths      | Rich text                             | Required        |
| Weaknesses     | Rich text                             | Required        |
| Comments       | Rich text                             | Required        |
| Pro comparison | Single line of text                   | Optional        |
| Photo          | Image file. Use this as primary image | Optional        |

### Contact table columns

| **Column**   | **Type**                                | **Requirement** |
|--------------|-----------------------------------------|-----------------|
| Contact type | Choice: Publicist, Agent, Doctor, Other | Optional        |

### Table relationships

| **Tables**             | **Type**    |
|------------------------|-------------|
| Contact to Player      | Many-to-one |
| Player to Scout report | One-to-many |
| Player to User         | Many-to-one |

### Forms and views

Build the appropriate forms and views for the data model you’ve built 
to be used in the model driven app.

-   Decide what columns need to be on the forms and in what order,

-   Decide what columns do you need to add/remove from your views, consider what
    columns should be read-only,

-   Evaluate if you need to present related tables as subgrids.

-   Decide if you should edit the default forms and views, should you create new
    from existing forms and views, or should you create them from blank.

-   Enable column security for the **Drug test result** and **Last drug test**
    columns.

### Security roles

Create a security role that allows scouts to:

-   Create, edit players and contacts.

-   Edit their own scouting reports and create scouting reports.

Create a column security profile that allows scout managers to:

-   Read, update, and create permissions to the Last drug test and Drug test result columns.

## Check your work
1.	Open the Player table and create a new row by populating the First Name, Height, and Weight. Confirm that the Last Name is required to create a Player row. Populate the Last Name and save to create the Player.
2.	Open the form you created for the Scouting report. In the Player lookup, locate the Player you created in the previous step. 
3.	Open the security role you created for scouts. For scouting reports, validate that scouts have access to edit and create rows. 