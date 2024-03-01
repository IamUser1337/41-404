Several activities should be performed prior to go-live:

- Performance testing
- Deployment planning
- Risk assessment

## Performance testing

Performance testing helps ensure that the application is performing as designed and can handle the rigors of daily use. Strong performance is vital for user adoption. Users will be reluctant to use an application that takes too long to load pages or go through business processes. Performance testing helps the customer identify if they need to revisit certain customizations and perform tuning activities.

Many customers don't include performance testing to save on cost and effort. Consequently, they will run into user adoption problems quickly after the application goes live. The solution architect needs to make the customer aware of the risks of not doing performance testing.

The results of this testing might require that the solution architect helps plan the remediation steps and guide them through submitting support requests. Performance testing needs to be completed well in advance of the application going live to remediate issues that occurred in performance testing.

Key questions that the solution architect should address for performance testing:

- Do you have a dedicated environment for performance testing?
- Have you identified the required master or reference data for performance testing?
- Have you identified the key business scenarios and the baseline for these scenarios?
- Have you identified the concurrent load for performance testing?
- Have you identified locations to perform latency tests for each location?
- Do you have a plan to populate the required data before performance testing?

The solution architect should:

- Identify potential hotspots in the app that should be performance tested.
- Know what the peak volume might be and always plan for slightly higher.
- Ensure that contractual performance service-level agreements (SLAs) are tested to ensure compliance.

The solution architect should monitor network traffic for the different office locations. In particular, latency and bandwidth need to be checked to ensure that app performance is not adversely impacted by network issues. You can use Microsoft Azure Monitor and Azure App Insights to monitor performance of your apps.

## Deployment planning

Deployment of a solution will go more smoothly with some preliminary planning. The deployment plan consists of many activities to ensure successful deployment of the solution. Deployment plans vary on a case-by-case basis, but a deployment plan can include:

- Environment setup
- Types of testing
- User training
- Data migration
- Rollout strategy
- Support during deployment

Depending on project size, the solution architect might own the deployment plan or act as an advisor to a dedicated planning team. Typically, the solution architect does not create the deployment plan but provides input and review.

The solution architect is often the first call when the customer is unhappy with the progress on deployment.

The solution architect should:

- Ensure that the sequence of events for go-live are in place.
- Look for risks consistently and have an alternate plan.
- Ensure that the team is in place to support the deployment.

## Risk assessment

The solution architect knows the system better than anyone; therefore, they should perform their own risk assessment for go-live. The solution architect should examine the system from top to bottom and then consider the following questions:

- What could break?
- What might not work as designed?
- What if the other system goes down?
- Do we have the proper deployment sequence?

A solution architect should always plan for the worst and celebrate later when it doesn’t happen.
