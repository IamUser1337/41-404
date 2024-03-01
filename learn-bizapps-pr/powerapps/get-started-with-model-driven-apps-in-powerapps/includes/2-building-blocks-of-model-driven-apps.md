A well designed model-driven app consists of several components you select using the designer to build the appearance and functionality of the finished app. The components and component properties that makers use to create an app become the metadata.

To understand how each of these components relates to app design, we can categorize them as data, user interface (UI), logic, and visualization components.

## Data components

These components determine what data the app builds on and the designer used to create or edit the component.

Data components are either designed at a table level within an environment, or within a solution contained within the environment. See the descriptions in the table below of each type.

| Component        | Description | Designer |
|------------------|-------------|----------|
| Table           | A container for records with properties that you track, such as a contact or account. Many standard tables are available. You can customize a nonsystem standard table (production table) or create a custom table from scratch. | Power Apps table designer |
| Column            | A property that is associated with a table. A column is defined by a data type, which determines the type of data that can be entered or selected. Examples include text, number, date and time, currency, or lookup (creates a relationship with another table). Columns typically are used with forms, views, and searches. | Power Apps table designer |
| Relationship     | Table relationships define how tables can be related to each other. There are 1:N (one-to-many), N:1 (many-to-one), and N:N (many-to-many) types of relationships. For example, adding a lookup column to a table creates a new 1:N relationship between the two tables and lets you put that lookup column on a form. | Power Apps table designer |
| Choice column | This is a special type of column, which provides the user a set of predetermined options. Each option has a number value and label. When added to a form, this column displays a control for the user to select an option. There are two kinds of choices; choices, where the user can only select one option, and multi-select choices, which allow more than one selection. | Power Apps option set designer |

## UI components

These components determine how users will interact with the app.

| Component | Description | Designer |
|-----------|-------------|----------|
| App       | Determines the application fundamentals such as components, properties, client type, and URL for your app. | App designer |
| Site map  | Specifies the navigation for your app. | Site map designer |
| Form      | A set of data-entry columns for a given table matching the items that your organization tracks for the table. For example, a set of data-entry columns where users input relevant information to track a customer's previous orders along with specific requested reorder dates. | Form designer |
| View      | Views define how a list of records for a specific table appears in your app. A view defines the columns shown, the width of each column, the sort behavior, and the default filters. | View designer |
| Custom page (preview) | A canvas based page allowing a more flexible layout, low-code Fx functions, and Power Apps connector data | Canvas designer |

## Logic components

These components determine business processes, rules, and automation the app will have. Power Apps makers use a designer that is specific to the type of process or rule.

| Type of logic         | Description | Designer |
|-----------------------|-------------|----------|
| Business process flow | An online process that walks users through a standard business process. For example, use a business process flow if you want everyone to handle customer service requests the same way, or to require staff to gain approval for an invoice before submitting an order. | Business process flow designer |
| Workflow              | Workflows automate business processes without a user interface. Designers use workflows to initiate automation that doesn't require any user interaction. | Workflow designer |
| Actions               | Actions are a type of process that lets you manually invoke actions, including custom actions, directly from a workflow. | Process designer |
| Business rule         | Used to apply rule or recommendation logic to a form, such as to set column requirements, hide columns, or validate data. App designers use a simple interface to implement and maintain fast-changing and commonly used rules. | Business rule designer |
| Power Automate Flow | Power Automate is a cloud-based service that lets you create automated workflows between apps and services to get notifications, sync files, collect data, and more. | Power Automate |

## Visualizations

Determines what type of data visualizations and reporting the app will have available.

| Component                   | Description | Designer |
|-----------------------------|-------------|----------|
|Chart                        | A single graphic visualization that can be displayed within a view, on a form, or be added to a dashboard. | Chart designer |
|Dashboard                    | Functions as a palette for one or more graphic visualizations that provide an overview of actionable business data. | Dashboard designer |
| Embedded Power BI | Add embedded Power BI tiles and dashboards to your app. Power BI is a cloud-based service that provides business intelligence insight. | Combination of chart designer, dashboard designer, and Power BI |

> [!div class="mx-imgBorder"]
> [![Screenshot example of visualization components with charts.](../media/updated-dashboard-designer.svg)](../media/updated-dashboard-designer.svg#lightbox)
