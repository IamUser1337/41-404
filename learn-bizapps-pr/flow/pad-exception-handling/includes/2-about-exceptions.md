Exception handling is the mechanism that allows Power Automate for desktop to handle and recover from unexpected circumstances and issues that might occur while a flow is running.

In the example we explored in the introduction of this module, consider the scenario where the client database cannot be accessed because of a network issue. Attempting to connect to the database would then cause an exception, and the flow would then stop running, producing an error.

In this unit, you'll learn about exceptions and how they can be handled.

## Exceptions

Exceptions are events that occur while a flow is running; these events disrupt the expected flow of actions, and cause it to fail if they are not handled properly. Exceptions occur when an action cannot run as intended, and may be caused by various factors: incorrect inputs, unexpected values, software/hardware failures, unavailable resources, etc.

## Handling exceptions

When an exception occurs, the default behavior would be to stop the flow, and generate an error. However, this behavior can be modified, so as to remedy the situation and prevent the flow from stopping.
