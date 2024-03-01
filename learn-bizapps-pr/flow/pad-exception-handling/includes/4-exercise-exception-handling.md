Exception handling is implemented in already developed flows, after risks have been identified by testing.

To implement the following exercise, you can create a new flow containing only a **Download from web** action. The flow in the example is set to download the Windows 10 media creation tool, but you can configure the action to download any file.

![Screenshot of the Download from web action.](..\media\exercise-download-from-web-action.png)

After developing the main subflow, create a new subflow named **Check_Web_Access**. The subflow should check if the server you want to use is available. 

To achieve this functionality, use the **Ping** action to check the server. Next, use an **If** block to check if the response indicates that the server is available. When the **Ping** action returns **Failure**, the flow should stop.

![Screenshot of the Check_Web_Access subflow.](..\media\exercise-check-web-access-flow.png)

Optionally, you can use the **Get current date and time** and **Write text to file** actions to append a new registry to a log file.

![Screenshot of the optional actions in the Check_Web_Access subflow.](..\media\exercise-check-web-access-flow-optional.png)

## Set up exception handling for an individual action

Back to the main subflow, the **Download from web** action could be a potential risk, as internet connectivity issues may cause the flow to fail.

To make the action robust to connectivity issues, open its properties and select **On error**. Then, configure the following options:

-   Retry policy Fixed

    -   Times: 1

    -   Interval: 2

-   Run the **Check_Web_Access** subflow

-   Continue flow run, by repeating the action.

![Screenshot of the error handling options of the Download from web action.](..\media\exercise-download-from-web-action-on-error.png)

This error handling configuration makes the action retry after 2 seconds every time it fails.

If the retry is unsuccessful, the **Check_Web_Access** subflow is run. The subflow checks if the server is available. If it isn't, the flow stops. If it's available, the action is rerun.

## Set up exception handling for a block of actions

Having ensured that the **Download from web** action runs as intended, let's add two more actions in the main subflow.

Deploy the **Copy file(s)** action and configure it to create a copy of the downloaded file on a second hard drive on your desktop. Next, use the **Rename file(s)** action to change the name of the newly created file.

![Screenshot of the final main subflow.](..\media\exercise-main-subflow.png)

While executing the flow, the second drive may be disconnected. This scenario will cause the flow to fail. To avoid failure, you have to implement a common exception handling behavior for both actions, as the risk is the same.

Add an **On block error** action before copying the file and configure it to skip the actions inside the block.

![Screenshot of the On block error action.](..\media\on-block-error-action.png)

Now, if any error happens while copying or renaming the file, the flow will skip these steps and continue running.
