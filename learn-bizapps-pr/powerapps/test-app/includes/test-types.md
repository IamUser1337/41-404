> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE50N9W]

In this section, you'll learn about the basics of how to complete testing on your app.

## Unit tests

You can use a *unit test* to check whether a specific function or feature of your app is working correctly. These tests are repeatable and run programmatically within fractions of a second. Briefly, unit testing ensures that the code that's included within your solution works as expected.

## End-to-end tests

*End-to-end tests* will help you check whether the overall solution runs correctly. This factor is important because, though all unit tests function correctly, the integration between two units can potentially fail. You can complete these tests by following a test scenario that's close to the use case of the actual business process.

The resulting solution might not involve custom code; therefore, the need for unit testing might not have a great appeal. However, end-to-end tests will always be a requirement before you release your solution to users within the organization.

## User acceptance tests

App users will administer the *user acceptance test* (UAT) rather than the maker. This test ensures that the app that's been built by the maker matches the requirements that were initially requested by the user.

To get good results from UATs, make sure that you:

-   Test with real users.

-   Try to choose users who have diversity in terms of IT skill levels. As a result, you'll receive various feedback.

-   Don't give the user instructions; observe whether they can understand the app intuitively.

-   Observe how users navigate the app without assistance, and determine where you can improve the design.

-   Ask the user to explain their expectation in a scenario when they're stuck on a screen.

-   Experiment with different devices to make sure that the test cases behave similarly.

-   Test the app in the user's actual environment or location if the app uses offline capabilities. This situation is ideal.

-   Ask your users to attempt "breaking" your app, such as by entering unusual characters in text fields.

-   Ask users to test more challenging scenarios. Typically, users will test the "happy path" (the path that a user takes when everything runs perfectly). Instead, ask users to test other scenarios, such as canceling an expense report instead of submitting it or denying an expense report instead of approving it.

Your users might not be familiar with testing software. Inform them of the type of feedback that you're looking for. It's often helpful to provide a template for bugs to make sure that testers explain exactly what they were doing, what happened, what they expected to happen instead, and other relevant information about their testing environment (such as device type and browser).

It's natural and acceptable for the user to request changes to the specifications or ask for other features.

These requests should be recorded in the feature list that's described in [Prioritizing features and requests](/power-apps/guidance/planning/prioritizing-features/?azure-portal=true).
