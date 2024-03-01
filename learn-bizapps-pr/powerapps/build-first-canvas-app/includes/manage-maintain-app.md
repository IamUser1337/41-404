Congratulations, you're now an app creator.

In this unit you'll learn, at a high level, how to manage and maintain your new app. Additionally, you'll learn about app sharing, versions, data sources, connections, and helpful tips to help ensure a successful app rollout.

Your first task will be sharing your app.

## Share the My Expenses app

As the app creator, you're the only person who has access to the app; that is, until you decide to share it with other users in your organization. Even if users had the link to the app, without the app being shared with them, they would only receive an "Access denied" type of message. For those users whom you want to share the app with, go to the [**Power Apps home page**](https://make.powerapps.com/?azure-portal=true), and then watch the following demonstration.

> [!div class="mx-imgBorder"]
> [![Demonstration of the My Expenses app functionality.](../media/expenses-app.gif)](../media/expenses-app.gif#lightbox)

> [!NOTE]
> As a new app creator, or even an experienced app creator, before you release the app to everyone, make sure that it goes through some type of UAT plan. This approach will help you catch potential issues or bugs in the app and get them fixed. Your users' first impression of the app will be crucial to ensuring a strong user-adoption rate and the overall success of the app.

## App updates and versions

Over time, your app(s) will require you to make updates, such as adding new functionality, reworking existing app functionality, or implementing new feature(s) based on Microsoft updates. Office 365 and Power Apps are constantly changing. Keeping up with the changes is important so that you can determine whether to apply these updates to older apps or not. Similar to a car or truck that needs regular servicing and maintenance, so do your apps to ensure that they're performing as expected. Therefore, as new features and/or controls become available, you should review older apps that you've built before this feature to determine whether it's worth implementing or not.

## Data sources and connections

In Power Apps, most canvas apps use external information that's stored in data sources. A common example is a table in an Excel file that's stored in OneDrive for Business or SharePoint. Apps will access these data sources by using connections. Some connections allow Power Apps to read and write stored data. In Power Apps, you can add many data sources to your apps through built-in or custom connectors. The following figure shows some of the most popular data sources.

> [!div class="mx-imgBorder"]
> [![Screenshot of the list of available data sources in Power Apps.](../media/data-sources.png)](../media/data-sources.png#lightbox)

Many data sources are cloud services, such as Salesforce. Even Twitter can be a data source if, for example, you're tracking your company's hashtags. Connectors might not seem like the most exciting part of app development; however, they're essential when you work with data that you, your colleagues, and your customers care about. When an app shows up with your data source for the first time, you might suddenly find that they are, in fact, exciting.

For data that's stored on-premises instead of in the cloud, you can use a gateway to provide a reliable connection between Power Apps and your data source. The gateway sits on an on-premises computer and communicates with Power Apps.

An advantage of building your business apps in Power Apps is being able to connect to many data sources in a single app. With the connectors in Power Apps, you can connect to where your data lives. For more information, see [Work with data in a Power Apps canvas app](/training/paths/work-with-data-in-a-canvas-app/?azure-portal=true).
