Exceptions may occur from virtually any action. For this reason, most actions’ properties contain an **On error** button. This button allows access to the action's exception handling settings.

## Action-level exception handling

In the initial example, we mentioned that the client's database may be inaccessible, causing the action that communicates with the database to produce an exception.

To prevent this, open the action’s properties, and press the **On error** button.

![Exception Handling in the Open SQL Connection action's properties.](..\media\open-sql-connection-action-properties.png)

In this view, you will be able to configure the action’s exception handling behavior, by either activating preset rules, or adding new ones. These rules come into effect if this specific action fails, and in the order in which they are arranged:

![The populated Exception Handling tab in the Open SQL Connection action's properties.](..\media\open-sql-connection-action-properties-all-exceptions.png)

> [!NOTE]
> You can drag and drop any user-created rules to rearrange them.

In the above case, for example, when this action fails, it will retry one more time after 2 seconds, and then run a subflow that will send an email to notify the administrator about the database status. Additionally, the action will change the value of a variable that indicates that the database is down.

By default, exception handling takes effect when any exception occurs while this action is running - however, you can configure it so that exception handling occurs only on a specific type of exception. Each action has specific exception types that it may produce:

![The populated Exception Handling tab in the Open SQL Connection action's properties with selected exceptions.](..\media\open-sql-connection-action-properties-selected-exception.png)

In this example, the exception handling rules will only apply when the **Can't connect to Data Source** exception occurs.

## Block-level exception handling

There are cases where one cannot be certain which action is at risk of failing, and it is not practical to apply the same exception handling rules to every single action.

For example, consider a flow in which Power Automate for desktop interacts with the web portal. If at any point during this task the portal or browser becomes unresponsive, the preferred action is to close the browser, launch it again, and restart the entire web portal interaction from the beginning. However, a web portal interaction can span tens, or even hundreds of actions; so assigning the same exception handling rules to each action individually is impractical.

The **On block error** action allows you to apply one set of exception handling rules to an entire block of actions:

![The On block error action's properties dialog.](..\media\on-block-error-action-properties.png)

Actions in between the **On block error** and **End** actions are affected by the block’s exception handling rules:

![The Workspace with an example using the On block error action.](..\media\exception-block-workspace.png)

In this example, if any of the actions within the block fails, the block’s rules will take effect; a subflow that closes the web browser will run, and the entire block will be repeated, thus preventing the flow from crashing due to a non-responsive web page or browser.

## Exception handling priorities

The order in which exception handling is applied is from the bottom up; this means that, in case an action fails, its individual exception handling rules will take effect immediately. If that is not enough to resume the flow, any block-level exception handling will take effect.

Therefore, any action-level exception handling rules run before the respective block-level rules.
