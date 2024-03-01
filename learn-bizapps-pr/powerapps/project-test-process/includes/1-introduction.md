A solution architect's work continues after the system has been designed. Their next task is to ensure that the system is deployed and used by real users.

## Solution architect role in testing and go-live

Typically, the solution architect is one of the people who knows best how the solution works and can guide the test team in how to test it.

The solution architect has a key role in testing and should:

- Stay involved until the end of testing to ensure success.
- Help educate the testing team on the solution architecture to ensure that they adequately test all components and integrations.
- Triage complex problems that arise during testing, dry runs, and after go-live.
- Participate with the go-live team in planning and implementing the go-live strategy.

## Overview of testing

Proper testing is important to help ensure the project's success.

> [!NOTE]
> Testing must be an ongoing effort from the first component that is built until go-live; it can't be a one-time, big exercise.

Testing is more than the process of mapping requirements to functionality. While it's important to build and implement these types of tests, more aspects of a solution should be tested as well. Regardless of the specific metric that is being tested, the process is similar.

![Diagram of the test process of plan, prepare, execute, and report.](../media/1-test-process-c.png)

The testing process includes the following steps:

- **Plan** - Review the overall test strategy, develop the test plan, and perform needed analysis for baseline metrics. Identify key business scenarios that are in and out of scope. Document the requirements, if that step has not already been completed.

- **Prepare** - Set up needed environments for performance testing, user acceptance testing, and so on. Review data that is received for migration, before and after the migration testing. Validate high-level system requirements, and then develop needed scripts.

- **Execute** - Run test scripts, analyze results, identify potential bottlenecks, and then review failures and behaviors.

- **Report** - Prepare a detailed assessment of the reporting plan, results, and plan of action.

## Types of testing

The solution architect should be part of the discussion regarding the amount and type of testing that is required for a project.

Common types of tests in Microsoft Power Platform include:

- **Unit tests** - Performed by the app builder, business analyst, functional consultant, or developer.

- **Functional tests** - Verify that the implementation meets requirements.

- **Acceptance tests** - Performed by users to give formal approval.

- **Regression tests** - Tests the unchanged functions for regression and are typically performed whenever a system update has occurred.

- **Integration tests** - The goal is for all integrated systems to work in harmony. Integration testing verifies that everything works together, including integrated services and data from other sources.

- **Performance tests** - These tests are verified with expected peak load and peak transaction volume and are typically automated and run before go-live.

- **Migration tests** - Practice data migration to ensure data quality. These tests are performed in close consultation with subject matter experts that know the customer data. These experts should understand the data transition and transformation and can confirm that the migrated data is valid with proper context.

- **Disaster recovery tests** - A disaster recovery plan is useless if it doesn’t work.

- **Go-live tests** - Dry runs of the complete solution and go-live process. These tests are typically performed before go-live.

Not all types of testing will be required; it's determined by the size and scope of the project.

### Unit testing

You can use a unit test to check whether a specific function or feature of your app is working correctly. Typically, app makers and developers perform unit testing. Each team member should check their own work before the handoff.

Unit testing is recommended but not required. When you are getting started, or if the amount of code in your solution is relatively small, you might perceive that you are spending more time writing tests than creating the functionality that is included in your solution. The benefits of unit testing begin to accrue when your solution becomes larger and more complex, particularly with server-side development, where you could see significant benefits in debugging locally by using mock or fake data with a testing framework.

Manual testing can be done with all apps, business rules, and plug-ins. Some tests can be automated by using the Microsoft Power Apps Studio and Visual Studio. A popular unit test framework for server-side development is Fake Xrm Easy.

The solution architect should decide on the tools that will be used for unit testing and the level of automation that should be used.

### Integration testing

The solution architect needs to help the test team understand how to test the integrated components.

One advantage of Microsoft Power Platform is its strong integration capabilities. Integration is one of the most important aspects of the business process implementation because it ensures that the implementation functions correctly and has a strong impact on overall adoption.

The solution architect and customer should review the testing scenarios that involve integrations with other line-of-business applications to ensure that end-to-end testing scenarios are created. This review will likely require that the customer plans to have test environments for their other applications.

Each integration will likely have its own test approach, and it needs to be defined. The testing team should be involved early to determine how they'll test each integration scenario. The teams need to ensure that the necessary integrations can be configured to support testing.

A key aspect of integration testing should be focused on the data that flows in and out of the integration. Much of the discussion in the data validation testing section can also apply to the data that is involved in integrations.

Because integration testing can involve other systems, you need to ensure that test environments are used for all components. You don't want integration testing to communicate with a live system and then modify the production data by accident. Occasionally, test scenarios will drive configuration options in the application integration to make it testable. Having the ability to turn off integrations can help you test without invoking the integration.

The process of building integrations is now more approachable and is therefore more accessible to a greater number of people on project teams. Often, integrations might become hidden inside of Power Apps canvas applications or Microsoft Power Automate flows. These hidden integrations can often go unnoticed because the application is using a surface connector from another source. The plan should consider these integrations like any other integration and then test them accordingly.

### User acceptance testing

User acceptance testing (UAT) is performed by users to give formal approval and to test the usability of the system. Acceptance testing is typically performed as a final check before you roll out functionality. This test is to ensure that what has been built by the makers will match the requirements that are initially requested by the user.

Tips for getting good results from UAT:

- Test with real users.
- Choose users with diversity in terms of IT skill levels. Consequently, you can get various feedback.
- Don't give the user instructions; see whether they can understand the app intuitively.
- Observe how the users navigate the app without assistance, and then determine where you can improve the design.
- When the user is stuck on a screen, ask them to explain their expectation.
- Experiment with different devices to make sure that the test cases behave similarly.
- Ideally, test the app in the user's actual environment or location if the app uses offline capabilities.
- Ask your users to attempt "breaking" your app, such as by entering unusual characters in text columns.
- Users will typically test the "happy path" (the path that a user takes when everything is going perfectly). Ask them to also test scenarios such as canceling an expense report instead of submitting it or denying an expense report instead of approving it.

Users might not be familiar with testing software. Inform them of what type of feedback that you're looking for. It's often helpful to provide a template for bugs to make sure that testers explain exactly what they were doing, what happened, what they expected to happen instead, and relevant information about their testing environment (such as device type and browser).

The solution architect will be required to help triage issues that are raised by the users during testing.

### Security testing

Security testing is important to ensure the security of the application and alignment with regulatory requirements. This testing should include a vulnerability assessment to ensure that the application is secure. It should also include testing from the security context of different types of users to ensure that an appropriate level of data and features are available.

Security testing should also look at the security model inside the application for access to its data and features. Testing should include scenarios with different users who have different roles and access characteristics to ensure that the security model holds up. Security model testing should make sure that over sharing or under sharing isn't happening. One way to approach security model testing is to create a dedicated test user account for each major role set.

The solution architect should help define the level of security testing to perform.
