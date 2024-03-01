A fit gap analysis identifies the difference between the known requirements and the proposed (or current) solution. It shows us what is missing so we can address it. In order to address what is missing, you need to fully understand the requirements and analyze the moving parts of your proposed solution.

How we address the identified gaps will vary for many reasons; time, budget, resources among the most common influences. Below we see the trade-off triangle. With the triangle, the rule is simple. If one side changes, at least one other side must also change.

Fit gap analysis is simply a process to help you identify what needs to be done and to help size and prioritize. Some projects and methodologies do this explicitly and call it out, others accomplish the same result with different steps that might not be called fit gap. In fact, you will probably begin to catch yourself doing it in your head as you mentally size up a requirement for how you would solve it.

Fit gap analysis makes sense when you are starting with some level of existing functionality. For business applications like Dynamics 365 that have a lot of built-in functionality it’s important because where there is a “fit” meaning it already solves the requirement it’s important to identify and not re-create it with custom developed feature. That also means it’s important that who is performing the fit gap analysis has a good understanding of the app out of the box features.

The mechanics of doing the fit gap analysis can vary greatly from doing it in your head on a small project to using a Microsoft Excel template, or perhaps using Azure DevOps work items and capturing it inline. The tool used should help the process and not make it more difficult, but the real value is in the output from the analysis.

To perform a fit gap analysis, you should look at each requirement/user story and note at least the following for each:

 -  **Severity of the gap or category** – This process categorizes each item as either being a fit, configured, custom, or other. The exact categories are up to your own descriptions. The goal is to broadly look at how much out of the box features you are using versus how much you have to customize.
 -  **Level of effort** – The level of effort helps size the amount of work for the item, which could be low, medium, high, or could be 1-10. Some teams even use things like t-shirt sizes or planning cards. The important thing here is to be consistent.
 -  **Priority** – Often this level comes from the business, but the architect often needs to have some prioritized higher to help with the architecture foundation being put in place.
 -  **Implementation notes** – This process describes the work to close the gap identified and backs up your assumptions you made in the other columns. For example, “Add a N:1 relationship to contact” might be enough to indicate it’s a configure category and what work is envisioned needs to happen. This is not detailed design specifications, but more of a high-level backup for the fit gap analysis results.
