A major obstacle for users who are translating their process from an Excel spreadsheet to a canvas app is the data model. People have become accustomed to considering data in a certain way; however, that approach might not work with newer technology. For example, in this module’s scenario, you're tracking expenses where you have information for every trip expense report and for each individual expense. You might be tempted to put all information together into a single table because the report exists in a single spreadsheet. However, that approach won’t optimize this particular solution.

One method that you could use is to build this report into a single table:

**Table Name:** Expense Report

**Columns:**

-   Traveler First Name

-   Traveler Last Name

-   Traveler Email

-   Trip Destination

-   Departure Date

-   Arrival Date

-   Expense

-   Category

-   Chart of Accounts

-   Transaction Date

-   Amount

-   Total

This approach would work; however, you would be repeating the same information, such as the traveler name, email address, and the trip details. Instead, you could make the information that stays constant into the focus of the line, as follows:

**Table Name:** Expense Report

**Columns:**

-   Traveler First Name

-   Traveler Last Name

-   Traveler Email

-   Trip Destination

-   Departure Date

-   Arrival Date

-   Expense 1

-   Category 1

-   Chart of Accounts 1

-   Transaction Date 1

-   Amount 1

-   Expense 2

-   Category 2

-   Chart of Accounts 2

-   Transaction Date 2

-   Amount 2

-   Expense 3

-   Category 3

-   Chart of Accounts 3

-   Transaction Date 3

-   Amount 3

-   Total

This data setup doesn't repeat information, but it still contains a problem. Now, the number of expense items that you can list in a single report are limited. Although you added several columns to cover expense items, you're still limited, which will create a table that could be confusing and difficult to work with.

Instead, consider the following setup:

**Table Name:** Expense Report

**Columns:**

-   Expense Report ID

-   Traveler First Name

-   Traveler Last Name

-   Traveler Email

-   Trip Destination

-   Departure Date

-   Arrival Date

-   Total

**Table Name:** Expense Report Details

**Columns:**

-   Expense Report ID

-   Expense

-   Category

-   Chart of Accounts

-   Transaction Date

-   Amount

By dividing the expense report into two tables, you have created a clean data setup that doesn't repeat information or limit the number of expense items that you can add. You can relate the tables together by using the **ID** field of the primary table, which you can store on the Details table. This table relationship is known as a parent/child relationship. The Expense Report table is the parent, which contains a single record or item for each report, and the Expense Report Details table is the child, which contains several records for each report.

While calling it a parent/child relationship helps show how these tables relate, you might be familiar with other terms to classify relationships, such as a one-to-many (1:N), one-to-one (1:1), or many-to-many (M:N). In this example, you have a one-to-many relationship, where one record in your Expense Report table relates to many records in your Expense Report Details table. Referring to relationships in this way can help you quickly discern how tables relate to one another when you are making a larger data model.

As your solution expands, you can add more tables with different relationships to expand functionality in your application. Additionally, all tables will need an identity column, sometimes referred to as a primary key. The following screenshot shows an example of what the completed data model might look like.

> [!div class="mx-imgBorder"]
> [![Diagram example of a completed data model.](../media/data-model.png)](../media/data-model.png#lightbox)

The preceding image shows that a User's table has been added. This addition has been made so that a user doesn't need to enter information that the system will already know. Furthermore, the user doesn’t need to enter their information whenever they have a new expense report. A status field has also been added so that travelers will know what stage of the approval process that their expense report is in. You can expand further to include an approvals table to track the time and date of various approvers or add more types of expenses, but those details won't be covered during this learning path.
