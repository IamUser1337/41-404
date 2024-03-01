As you collect requirements, they are commonly referred to as either functional or non-functional. Functional requirements describe what the solution needs to do or its behaviors, and non-functional are commonly used to describe non-behavior aspects of the solution such as performance requirements. In this lesson, we will cover some things to consider for functional requirements.

Each functional requirement should clearly capture the who, what and why of the requirement. If the requirement is too large, it should be broken down into smaller parts.

## Functional requirements

The following are a few simple examples of functional requirements:

 -  As a sales user, I need to be able to close an opportunity as lost, and capture why it was lost so that we can improve our sales tactics in the future.
 -  As a sales manager, I need to be able to approve a discount on a quote, so I can reduce the total price and give a discount to the customer.
 -  As a staff accountant, I want to be prevented from closing a batch that has pending items, so I do not have to re-open it later.

These examples communicate who, what, and why.

The following are a few examples of poorly worded requirements:

 -  Opportunities can be won or lost.
 -  Price should reflect discounts.
 -  From the Batch Item List, clicking the Close Batch button, which is the third button from the left, should close the batch if there are no items that would stop it from happening.

When gathering requirements of any variety, it is very helpful to map toward process or user journey, not just a list of features and functions. Build a story for a user and how they will successfully use the system you are designing. You can scribble on a whiteboard, use a tool to diagram a process, whatever works for your team at the planning stage you are in. Your team will dissect the pieces into smaller actionable items later.

### Acceptance criteria

Having a clear understanding of how a requirement is considered satisfied is important. Often, documenting this requirement will help determine if the requirement is detailed enough and right sized. This documentation is also helpful for the testing teams to evaluate the implementation of the requirement. And finally, it should be reviewed with the stakeholder to ensure it is accurate as it can be used to help prevent scope creep. It’s important to look for acceptance criteria that can’t possibly be met, and negotiate to reach a compromise that is achievable.

### Capturing exceptions

Commonly a simple requirement like closing a transaction might have a straightforward path and just a few exception paths. It’s important to look and identify these exceptions when capturing the happy path. As you move into design you don’t want to design primarily for exceptions. They should be handled as such, but if you do not know they exist you will have rework later. It’s also ideal to remember to capture how frequent the exception is, as some exceptions are best handled by procedure/process and not software customization.

### Avoiding scope creep

Left unchecked every project would add scope from what was envisioned and budgeted for. The project governance process should be used to evaluate how to handle these once identified. Often those accepted for inclusion might result in a change order depending on the project contractual structure. Simply ignoring that scope is increasing can easily result in project failure.

## Internationalization

Microsoft Power Platform offers makers many options to internationalize the apps. Model-driven apps and portal apps both come with internationalization options including language packs and multi-currency. Accurately documenting these requirements is essential for user adoption. Documenting the internationalization should begin with requirements and be included in quality assurance test plans, user adoption testing, and system documentation. Make sure to follow the best practices listed here for documenting actionable, testable requirements for internationalization needs as well.

## Solution artifacts

It is considered a best practice to give solution components logical names, and as you are preparing the documentation of such logical names, you will certainly see the value. Each project’s documentation of these items may be a little bit different than one another.

The goal of this documentation should be to ensure consistent continuation of the solutions as they evolve over time as well as keeping the project team informed. This is particularly helpful when you are participating in a team of makers and each team member is working on a different set of functionalities. Documenting the things that matter will be much easier if there are predictable names and consistent documentation of names and expected behaviors.

Project planning items such as user stories or backlog items can be good resources to help jumpstart your documentation. As tempting as it might be to wait to do this documentation until project completion, it will be a more helpful on-going resource if it is completed at least every project milestone. You will be able to notice and remedy inconsistencies and errors before they become bigger problems.

When documenting tables (either in a model-driven app, or with a Dataverse data source) consider including table description such as its intended use. Include the columns from each table, and their data type and description. Document the relationships between tables and the defined behaviors such as row deletion behaviors. Any considerations for security roles and column level security should also be included. Document views and their queries; forms and their target audiences/uses; reporting and dashboards.

Automation includes business process flows, Power Automate flows, business rules, and classic workflows. Not only should you document each of these separate automations, but you should also document how they work together. Connectors used and their requirements can be documented here as well.

Canvas apps components to document include specific screens and their navigation, data sources used, formulas, and triggers for automation. Power Apps portals have similar documentation needs as canvas apps but will also include differentiation between authenticated users and anonymous users.

When documenting Power Virtual Agents, include topic level conversation flow, targeted data sources, and escalation plans.

In addition to specific technical details, you may find it helpful to write narratives of the user journey. This is more than the “user clicks here”, and more of the expected experience in its entirety. Think of it as the story of that user’s day-to-day interaction with the solution. Considering the audience of this documentation, be mindful of considerations like accessibility in documentation and offering both words and graphical explanations. This documentation could be helpful for on-boarding new team members, creating user acceptance criteria and handing off the project to the customer at completion.

## Document data for migration and integration

Seldom do you start a project with no legacy considerations. Users have inefficient apps they are already using full of business data that they already understand. Depending on the exact circumstances, you can connect with the data, or migrate it. Either of these paths require planning and documentation.

Regardless of migration or integration, the quality of the data is very important. Is the data accurate? Is there old data that is no longer relevant? Are there duplicates to mitigate? Can we eliminate duplicates prior to migration?

Creating a checklist (and following it) will be helpful to minimize the effects of bringing the old data into the new solution.

**Document data sources:** Identify data source and connections used. Identify the quality of the source data. Identify columns that are being migrated, keeping in mind not all of the source data will be going in to the new system.

**Document data types:** Compare source data with destination schema. Identify potential transformation issues prior to beginning the movement of the data.

**Document data mapping:** Complete a column by column review of the data coming in to the system, confirm it is mapped correctly. Reconcile differences in source and target data column metadata.

**Document error handling:** Make a plan to remedy errors on import or integration.

**Accommodate for outliers:** Not everything will be an exact one-to-one mapping of the data from source to the new environment. Identify these outliers and make a plan.

**Document continual evaluation of data quality:** Review, report, and repair data quality.
