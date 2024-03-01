With model-driven Power Apps, you get an app designer with a standard user experience. With canvas apps, you have a near limitless design canvas. Both experiences require planning in order to achieve the best user experience. As mentioned previously, the functional consultant is often the bridge between differing roles on a project; this can include creating and documenting mockups of the user experience. The user experience is much more than a single screen, it is the entire user journey throughout the solutions that are built.

Considerations when designing the journey:

 -  **Consistency:** Is it jarring for the user to go between tasks and apps?
 -  **Logical progression:** Is the end to end-user experience designed with efficiency in mind? Should we consider branching some experiences for different groups of users?
 -  **Branding and theming:** Are the apps similar in appearance? Are there branding guidelines to follow?
 -  **Business processes and system automations:** Are the automations there to make things easier for the user? Do they actually make things easier for the user? The business processes and functionality implemented must meet the users’ expectations to achieve optimum user adoption. Is the new system making users’ lives easier and reducing steps that they need to finish processes, or is it adding additional steps to the process? Have we designed a system that uses automation of processes to ensure a consistent user experience?
 -  **Security:** Have we used built-in functionality to limit the user’s experience to only those things they should be doing? Security roles should be used to limit the forms, apps, and dashboards so users only see the application components that they need, and use model-driven apps to limit the views and other app components to just those needed when the user is working on the processes for which the app is designed.

As you design the user experience, keep in mind the ultimate goal, create an experience that is both useful and a joy to use. Many aspects of a solution drive user adoption. Not each of these is easily measured. Sadly, sometimes the best indication of user adoption is the failure to gain user adoption. Key areas that can determine the effectiveness of user adoption include:

 -  **Business value:** Business goals and strategy clearly defined along with the processes, success KPIs and business outcome for the project
 -  **Data and functionality:** Business process implementation within the platform meets (or exceeds) user expectation with respect to data, integration, security, reporting, etc.
 -  **Usability:** Application useability and client support user experience on web, Outlook, and mobile clients
 -  **Performance:** Overall application performance and reliability from end-user perspective to include page load time, time to save, errors, automation, etc.

## Business value

To achieve optimum user adoption, you first need to define the business use case for the system and your strategy for adoption of the system. Executive sponsorship should be identified for the project. It’s important that the deployment not be driven just by the IT department. A successful deployment requires alignment between IT and business stakeholders and they must all work together to deliver a solution that meets user expectations. All decisions that are made about system design and configuration should be made with user experience in mind.

### Individual value

Even if the business thinks that the system is designed well, achieves its goals and is a success; the user’s opinions must also be considered. The system should offer its users a delightful experience that helps them be more efficient.

## Data and functionality

Another major influencer on user adoption of the system, both positive and negative is the data in the system—the quality of data and the value of the data in the system. If you just forklift bad data into the system, the user experience in new system will be poor. To account for this, you should define a plan for the following areas:

 -  **Business data validation**: Is the data clean, is it the right data, and does it include only what is necessary for users to have a good experience and be able to do their jobs?
 -  **Data aging:** Is old, unusable, or expired data archived out of the system? Having complete enough data to do your job is important, but too much old data can make the system slow and difficult to use.
 -  **Data scrubbing and cleansing process:** How will you clean data that will be loading into the system, and what is your plan to keep that data clean in an ongoing basis?
 -  **Data integration and visual/UI integration**: What is the plan for ongoing data integration and are you using data integrations correctly? Is there data being copied into Dataverse that might be better as a visual integration, such as a virtual table or Microsoft Power Platform connector?

Users also need to be able to use the data in the system and need to understand the reporting and analytics options available to them in the system. This includes standard application components like Advanced Find, views, Excel export, report wizard, charts, dashboards, and templates. Users should also know what configuration options they have for these tools, such as creating personal views, templates, charts, and dashboards, as well as self-service analytics options in Power BI if applicable.

## Usability

You must be aware of the effects that the data model will have on the usability of the system and the end-user experience. Inconsistent design can provide a jarring user experience. Use the tools provided in the system to provide a consistent user experience.

Navigation should be logical and consistent so that users are comfortable with the system. If different forms have significantly different navigation experiences or related navigation links are not grouped, the users will be frustrated trying to use and navigate through the system. Everything users need for related system tasks should be grouped in the sitemap and form navigation areas. Form layout should be consistent and predictable . When possible always group similar columns, and tasks, in the same place for the user’s entire experience.

When building apps, they should be appropriately sized. You should not have a monolithic application with many unrelated business groups combined. Model-driven apps should generally address a single group or multiple groups that are directly related (such as a related sales and customer service process). Canvas apps should be used for simpler task-focused scenarios. If a user has to switch between multiple apps to complete a task the user will likely be frustrated, but if you try to use a large model driven app when the user needs to complete task focused activities on a mobile device, the user may also be frustrated. Make sure that your apps are properly sized and that they provide the best user experience for the way that your users will be working.

To fully empower all of your users to effectively use the app, you need to consider accessibility for users with disabilities. Make sure you fully understand the accessibility requirements of your users and that you are using the Solution Checker and App Checker to verify that your configuration meets or exceeds accessibility standards.

## Performance

System performance is another factor that is critical for optimal adoption of the system. If your solution is well built and your data is clean, but the system performance is poor, users will not want to use the system. The system must be responsive. The system must be dependable. The system must be robust and non-fragile.

Provide users with the training and support needed to reinforce good user adoption. Create a community of champions, including early adopters and super users. Provide effective user training—this training should be customized based on what types of training and knowledge transfer are most effective in your organization. This can include training materials, videos, knowledge base, and help resources that cover the application and processes. An internal helpdesk should be staffed with well-versed subject matter experts. This includes support during the deployment as well as after go-live.

Most Microsoft Power Platform projects are iterative. As the solutions grow through the iterations, keep in mind the good design principles you started with. At the end of the day, it is the user’s perception of the system we’ve built that defines their expectations. Work to understand their goals and the results as you design.
