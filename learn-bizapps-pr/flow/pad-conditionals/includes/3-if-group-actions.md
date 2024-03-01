The **If** group of actions is used when one or more conditions should be taken into account in order to determine the next steps of a flow.

Consider the following example: an Excel file contains incoming support ticket information, including urgency, and the customer’s subscription plan. Based on this information, the flow will determine the ticket’s maximum response time, and write it into the corresponding cell.

First, we open the Excel report and determine the range of the data. Then, we will loop through each row, reading the urgency and subscription plan:

![Screenshot of Read from Excel Loop action.](..\media\read-from-excel-loop.png)

Now, for each of these rows, the maximum response time must be calculated. The company’s service level agreements (SLAs) are as follows:

* Free users get a response within 30 days of submitting a ticket
* Basic users get a response within seven days
* Premium users get a response within one day

Also, any ticket marked as urgent must receive a response within 12 hours, regardless of the user’s subscription plan.

Since the information needed to figure out the maximum response time comes from more than one source, we will use an If conditional. We begin by assessing the ticket’s urgency, since it overrides the subscription plan in this case:

![Screenshot of If cell contains urgent dialog.](..\media\if-cell-contains-urgent.png)

![Screenshot of If cell contains urgent write 12 hours action.](..\media\if-cell-contains-urgent-write-12-hours.png)

Afterward, add each individual case as an alternative condition:

![Screenshot of Else if cell contains premium dialog.](..\media\else-if-cell-contains-premium.png)

Eventually, the flow will look like this:

![Screenshot of the Loop, If, Else if action.](..\media\if-else-if-final-structure.png)

Now, all scenarios have been covered. However, the flow should also address the case that there might be a value in the Excel file that is not one of the standard values. In such cases, we would like someone to look into the matter personally. For this reason, we will also add a final alternative:

![Screenshot of the completed Loop, If, Else if, Else action.](..\media\if-else-if-else-final-structure.png)

Now, in case of unexpected input, the maximum time will be designated as Undefined.
