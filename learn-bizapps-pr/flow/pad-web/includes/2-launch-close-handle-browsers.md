Before automating web components, you have to launch a web browser to indicate which web page to load and the desired launching mode.

Later in your flow, you can use the instance variable containing the launched browser to perform various operations through the available web actions.

Power Automate for desktop provides various launching actions to create browser instances for each supported browser:

- **Launch new Edge**
- **Launch new Internet Explorer**
- **Launch new Chrome**
- **Launch new Firefox**

All these actions accept similar input parameters and function virtually in the same way. Inside the actions, you can set the initial URL of the browser and the desired state of the window.

> [!NOTE]
> Power Automate for desktop may require additional configuration for some supported browsers. To find more information about browser configuration, please visit the [respective documentation article](/power-automate/ui-flows/desktop/using-browsers/?azure-portal=true).

![Screenshot of the Launch new Edge action.](..\media\launch-new-edge-action.png)

In the actions properties, you can also set whether the action will launch a new browser or attach to a running one. Through the **Launch new Internet Explorer** action, you have the additional option to launch the built-in automation browser.

![Screenshot of the automation browser option in the Launch new Internet Explorer action.](..\media\launch-new-internet-explorer-action-automation-browser.png)

> [!NOTE]
> The Power Automate for desktop automation browser implements some limitations that increase speed and efficiency on web-related flows. To find more information about the automation browser, please visit the [respective documentation article](/power-automate/ui-flows/desktop/using-browsers?azure-portal=true#using-the-actual-internet-explorer-vs-the-automation-browser).

When you've developed the web-related part of your flow, you can use the **Close web browser** action to close the browser. This action accepts a browser instance as an input parameter and doesn't return any outputs.

![Screenshot of the Close web browser action.](..\media\close-web-browser-action.png)

If you want to navigate to a new page using an existing browser instance, you can use the **Go to web page** action. In the action's properties, you have to specify the browser instance and the URL to load.

Additionally, you can use this action to reload the current page and move a page back or forward.

![Screenshot of the Go to web page action.](..\media\go-to-web-page-action.png)

In case you want to launch a page on a new tab, you can use the **Create new tab** action. In this action, you have to populate the browser instance and the URL of the web page to load.

![Screenshot of the Create new tab action.](..\media\create-new-tab-action.png)
