Previously you learned to use single-purpose functions to operate
against a table. Those are ideal and perform well, but sometimes you
need more flexibility or you need to do something that isn’t covered by one of those
functions. For those situations, there’s the **ForAll** function.

The **ForAll** function evaluates a formula for all records of a table.
The formula can calculate a value and/or perform actions, such as
modifying data or working with a connection.

Fields of the record currently being processed are available within the
formula. You can reference them by name as you would any other value.
You can also reference control properties and other values throughout your app.

For example, you could use ForAll(CustomerOrders,
Office365.SendEmail(Email, "Thank you", " You’re a great customer " & FirstName)) to send a separate email to all of the email addresses in the
CustomerOrders table. The email subject would be "Thank You" and the body would be "You’re a great customer" followed by the value stored in the
FirstName field.

This example varies from the **Concat** example in two important ways.
First, this will send one email for each record in the CustomerOrders
table. So, if there are 50 records, 50 different emails will be sent. In
the Concat example, only one email was sent with all 50 email addresses in
the To: line. Second, this email also references the FirstName field
from the CustomerOrders table. When you use the **ForAll** function, all
of the fields for each record are available to be used.

Things to know when using ForAll
--------------

With **ForAll** there’s a tremendous amount of power, but there are
also several things to know as you start to build your formula.

-   The formula can include functions that take action, such as
    modifying the records of a data source with the **Patch** and
    **Collect** functions.

-   You can't modify the table that is the subject of the ForAll
    function. This includes using **Patch** or **Collect** on the table.

-   The formula can call methods on connections.

-   You can perform multiple actions per record by using the ; operator.


-   When writing your formula, keep in mind that records can be
    processed in any order and, when possible, in parallel. You may
    process the first record of the table after the last record. Be sure to avoid ordering dependencies. 
    For this reason, you can't use
    the **Set**, **UpdateContext**, **Clear**, and **ClearCollect**
    functions within a ForAll function because they could easily be used
    to hold variables that would be susceptible to this effect. You can
    use **Collect**, but the order in which records are added is
    undefined.

The **ForAll** function has a lot more rules than most Power Apps
functions. Also, because you can’t use functions like Set and
UpdateContext sometimes you must find another way to approach your
formula. Often the reason you wanted to use **Set** with **ForAll** was
to track the number of records that were modified or to capture
information about those records. You may find that using Patch to update
a collection where you track that same data gets you the same result.

For more information about usage and rules for the ForAll function, see
[ForAll function in
Power Apps](/power-apps/maker/canvas-apps/functions/function-forall/?azure-portal=true).
