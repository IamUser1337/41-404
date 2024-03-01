Power Automate is a standalone component in the Microsoft 365 ecosystem but also a great Power Apps companion. This is because Power Automate has actions and triggers for interfacing directly with Power Apps. This connection allows you to easily use Power Automate functionality in your app.

## Business logic

Power Apps is great in scenarios where you have a direct action you want
to take after a user does an activity. An example might be
sending an email after a user submits a new expense report. If you need
to notify someone the expense report was submitted, then you can do that
easily directly from Power Apps.

But what if instead of just notifying someone, you also want to start an approval process? This is a great example of where connecting to Power Automate makes your app stand out. You can have Power Apps trigger a Power Automate flow when the user submits the data. Power Automate can then look up who the user's manager is, and send the manager an approval request. Power Automate will then help get a response from the manager, update the data source with the status based on their response, and send the original submitter an update.

Approvals are just one example of how you can use Power Automates native abilities to augment your app's capabilities.

## Data connections

Power Apps offers many options for connecting to data through built-in connectors, premium connectors, and custom connectors. However, sometimes you need more. Some data sources, like custom APIs, can provide data back in a difficult to use format. For example, complex JSON structures aren't user-friendly in your app. This is where Power Automate can help. Power Automate has other actions and expressions natively built in that are better at handling these complex data structures. And more importantly, these actions and expressions can parse through the data and restructure it into an easier-to-use object. After the data is parsed, Power Automate can respond to Power Apps with just the friendly data.

Use Power Automate to interact with complex data sources, restructure the objects, and then return to Power Apps only the data that you need. Watch this video to get started with creating a Power Automate flow to connect to Power Apps.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2ORdw]

The following video shows how to use Power Automate as a data source for your Power Apps app.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wsDJ]

Connecting Power Apps and Power Automate can bring greater functionality to your apps.
