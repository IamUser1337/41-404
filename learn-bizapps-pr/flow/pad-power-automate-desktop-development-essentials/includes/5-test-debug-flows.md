During flow development, it is important to test the behavior of the flow and ensure that everything is working as expected – and if not, to locate and diagnose the underlying issues.

## Testing

Flows under development can be run at any time in the flow designer, through the **Run** button; during this run, the current Action is highlighted, giving users a clear view of the run progress.

It is possible to run, stop, and resume the flow. It is also possible to run one action at a time, to closely examine the behavior of the flow in certain sections. This is all achieved using the respective buttons:

![Screenshot of the designer toolbar with Run and Run next action highlighted.](..\media\toolbar.png)

Breakpoints can be added to automatically pause the run when a specific action is reached; this is done by clicking to the left of the action in question:

![Screenshot of the main function breakpoint.](..\media\main-function-breakpoint.png)

On the bottom-right corner of the designer, the variables pane contains all the variables used in the flow; information about a variable can be viewed by double-clicking on it. This information is updated in real time, providing users a clear picture of the flow's state at any given time.

## Debugging

In addition to the above, certain features are designed specifically for locating and correcting errors.
Any design-time errors – errors that are identifiable before the flow is run – are communicated through red symbols in the designer, while details can also be found in the Errors pane at the bottom of the designer:

![Screenshot of the errors pane showing eight errors.](..\media\errors-pane.png)

In this example, two required fields were left blank, so the relevant action is highlighted as erroneous. The Errors pane contains further details.

Runtime errors – errors that occur while a flow is running – are communicated in a similar fashion:

![Screenshot of the runtime errors pane showing one error.](..\media\errors-pane-continued.png)

An incorrect value was passed as an Excel column; while trying to read from that column, the flow failed. The action in question is highlighted, and the Errors pane contains more detailed information on the error.
