Retrieve the current date and time with the **Get current date and time** action. The action can be set to only retrieve the current date. The **Time zone** property can be set to the system default or you can set a specific time zone from the drop-down list of available options. The result of the action configuration is stored in a datetime variable.

![Screenshot of the get current date and time action properties.](..\media\get-current-date-and-time-action-properties.png)

Add a specified amount of the selected time unit to a datetime variable with the **Add to datetime** action. The time can be added in seconds, minutes, hours, days, months, or years, and the result is set to a new variable.

![Screenshot of the add to datetime action properties.](..\media\add-to-datetime-action-properties.png)

Subtract dates using the **Subtract dates** action. The action subtracts **Subtract date** from **From date** and then stores the difference in days, hours, minutes, or seconds in a new variable.

![Screenshot of the subtract dates action properties.](..\media\subtract-dates-action-properties.png)

A variable of the data type **datetime** has the following properties:

|Property  |Description                                               |
|----------|----------------------------------------------------------|
|Year      |The year part of the **datetime** value.                      |
|Month     |The month part of the **datetime** value.                     |
|Day       |The day part of the **datetime** value.                       |
|DayOfWeek |The name of the day (for example, Sunday, Monday, and so on).    |
|DayOfYear |The day of the year part of the **datetime** value (1-365/6).  |
|Hour      |The hour part of the **datetime** value.                      |
|Minute    |The minute part of the **datetime** value.                    |
|Second    |The seconds part of the **datetime** value.                   |
