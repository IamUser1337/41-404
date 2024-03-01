Testing is more than the process of mapping requirements to functionality. While it is important to build and execute these types of tests, there are many more aspects of a solution that should be tested. Regardless of the specific metric being tested, the process is fairly similar.

A testing process usually follows the flow below:

1.  **Plan.** Review the overall test strategy. Develop the test plan. Perform needed analysis for baseline metrics. Identify key business scenarios that are in, and out of scope. Document the requirements if not already completed.
2.  **Prepare.** Set up needed environments, performance testing, user adoption testing, etc. Review data received for migration, both before and after the migration testing. Validate high-level system requirements. Develop needed scripts.
3.  **Execute.** Execute test scripts. Analyze results, identify potential bottlenecks. Review failures and behaviors.
4.  **Report.** Prepare a detailed assessment of the reporting plan, results, and plan of action.

## Types of testing

The functional consultant will likely be involved in some capacity in each of these testing types. Each one has potential make-or-break results and with the breadth of skills of the functional consultant they are a great resource to help the quality team in succeeding.

:::row:::
  :::column:::
    **Test Type**
  :::column-end:::
  :::column:::
    **Description**
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Unit tests
  :::column-end:::
  :::column:::
    These tests are performed by the app builder or code developer as an asset is built throughout the implementation process. These unit tests should be performed by whomever is actively building the functionality, which could be a developer, a functional consultant, a business analyst, and so on.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Functional tests/system tests
  :::column-end:::
  :::column:::
    These tests verify implementation meets requirements and does not have defects. Functional tests can be performed manually by customer or partner team resources or may be automated.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Acceptance tests
  :::column-end:::
  :::column:::
    These tests are performed by end users to give formal approval, and they test the usability of the system. Acceptance testing is typically performed as a final check before rolling out functionality. In an initial deployment, this testing is at the end of the project, but in an agile iterative deployment, functionality may be released each sprint, so you will need to conduct acceptance testing throughout the project. This testing is often called UAT, user acceptance testing.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Regression tests
  :::column-end:::
  :::column:::
    These tests evaluate non changed functions for regression and are typically performed whenever there is a system update. Customers need to have a plan to regression test before every major platform update (twice a year) to verify that current configuration works optimally post update. Regression testing can be automated.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Integration tests
  :::column-end:::
  :::column:::
    The goal is for all integrated systems to work in harmony. Integration testing verifies that everything works together including integrated third party services and data. This testing takes place following initial development of integrations.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Performance tests
  :::column-end:::
  :::column:::
    These tests verify system performance with expected peak load and peak transaction volume and are typically automated and run before go-live or before onboarding a large group of additional system users.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Data Validation tests
  :::column-end:::
  :::column:::
    These tests verify data migration to ensure data quality and are typically performed by the person who wrote the integration or customer resources in close consultation with subject matter experts that know the customer data. These experts should understand the data transition and transformation and can confirm the migrated data is valid with proper context. This process can involve standard checks like row counts or spot-checking a subset of data migrated to verify columns were correctly mapped. This process is also sometimes called data migration testing.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Disaster recovery tests
  :::column-end:::
  :::column:::
    These tests involve testing what happens if a disaster brings down your system. While Microsoft handles major disaster recovery for you, you need to ensure that you have a plan to resume operations after a disaster. For example, verifying that your source code is up to date so that you can recreate your dev environments successfully in case of a disaster.
  :::column-end:::
:::row-end:::
:::row:::
  :::column:::
    Go-live tests
  :::column-end:::
  :::column:::
    These tests include dry runs of the complete go live process and are typically performed before go-live.
  :::column-end:::
:::row-end:::


## The functional consultant's role in testing

In addition to participating in the actual testing process, you should be prepared to help in authoring test plans, or at least reviewing them. This process will help you do your job better by making sure expectations are aligned from beginning to end of the project lifecycle. It also helps the quality team by validating their test plans with your actions building and configuring the system.

While you may be involved in any of the testing listed, the functional consultant will likely be more involved in the following:

### Functional testing

The goal of functional testing is to ensure that the customer has identified a strategy around a set of user champions and test case scenarios that will be used by the test team for getting an assessment of the quality for their solution.

An important part of functional testing is ensuring a regression doesn't get introduced from any changes that continue to be introduced both before go-live and after go-live. From the full suite of functional tests, a subset should be identified as regression tests run on a regular basis for each release or update.

### Integration testing

the most important aspects of the business process implementation to function correctly and has a strong impact on overall adoption. The customer must ensure that they plan to engage owners from other applications that are integrated with the system. This testing will also require them to define clear roles and responsibilities to fix any issues or make changes as required.

Each integration will likely have its own test approach that needs to be defined. The testing team should be involved early to look at how they will test each integration scenario. The teams need to ensure as that the necessary integrations have the ability to be configured to support testing.

A key aspect of integration testing should be focused on the data that flows in and out of the integration. Much of the discussion in the data validation testing section can also apply to the data involved in integrations.

### User acceptance testing

User acceptance testing is critical to ensure go-live approval, as is acceptance of the new system post-go-live. It could also provide a backlog of feature requests that can be planned as part of post go-live enhancements.

Customers must ensure that user champions or key users have been identified early on and should be kept engaged throughout the project lifecycle. They should engage this group along with an additional user community to test the application. There should be a clear definition of the successful user acceptance criteria as this definition will also roll up into go/no go live decision.
