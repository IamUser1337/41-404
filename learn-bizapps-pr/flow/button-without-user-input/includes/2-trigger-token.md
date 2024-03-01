Trigger tokens are data points that are known and available to the
device on which the button flow is running. These tokens are dependent
on factors such as time and the geographic location of the device at a
given moment.

When you run a flow from a button on a smart phone, the date,
time, and current address where the phone is located are
automatically available for use. You can use these trigger tokens to
build useful flows that will minimize repetitive tasks such as providing
your location to someone or tracking how much time you have spent on a
particular job or service call.

The following table provides a list of button trigger tokens that are available for
you to use when creating your button flows.

| Parameter        | Description                                                                     |
|------------------|---------------------------------------------------------------------------------|
| City             | The city in which the device that's running the flow is located.               |
| Country / Region | The country/region in which the device that's running the flow is located.      |
| Full address     | The full address where the device that's running the flow is located.           |
| Latitude         | The latitude in which the device that's running the flow is located.            |
| Longitude        | The longitude in which the device that's running the flow is located.           |
| Postal Code      | The postal code in which the device that's running the flow is located.         |
| State            | The state in which the device that's running the flow is located.               |
| Street           | The street on which the device that's running the flow is located.              |
| Timestamp        | The time in the area where the device that's running the flow is located.       |
| Date             | The date in the area where the device that's running the flow is located.       |
| Username         | The username of the person who is signed in to the device that's running the flow.      |
| User email       | The email address of the person who is signed in to the device that's running the flow. |

Triggers can be added to both actions and conditions.

Consider a **Send an email (V2)** action where you have the option to
apply any of the parameters from the preceding table in the body of the email message.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Send an email action with Dynamic content showing fields like City, Date, and Full address.](../media/send-email-action.png)](../media/send-email-action.png#lightbox)

You can also apply the trigger in a condition on the left and right side.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Left side trigger condition, If yes.](../media/left-side-trigger-condition.png)](../media/left-side-trigger-condition.png#lightbox)

> [!div class="mx-imgBorder"]
> [![Screenshot of the Right side trigger condition, If no.](../media/right-side-trigger-condition.png)](../media/right-side-trigger-condition.png#lightbox)
