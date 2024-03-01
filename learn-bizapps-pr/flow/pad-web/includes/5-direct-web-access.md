Power Automate for desktop provides three actions that enable you to interact with APIs and run scripts on web pages. You can use these actions to implement custom behavior on web pages and communicate with APIs without creating complex flows to automate web pages.

## Download from web

Through the **Download from web** action, you can download text and files from web pages. To use this action, you need to specify the URL of the desired page and the appropriate method (GET or POST).

The action stores the returned text into a variable, while the downloaded files are saved locally.

![Screenshot of the Download from web action.](..\media\download-from-web-action.png)

## Invoke web service

In case you want to communicate directly with web services and APIs to reduce the complexity of your flows, you can use the **Invoke web service** action.

Every web service comes with API documentation that specifies the appropriate input parameters. The use of invalid parameters might cause an exception.

The action stores the text responses into a variable, while the retrieved files are saved locally.

![Screenshot of the Invoke web service action.](..\media\invoke-web-service-action.png)

## Run JavaScript function on web page

If you want to execute custom behavior through scripts, you can use the **Run JavaScript function on web page** action. This action accepts a browser instance and a JavaScript function as inputs and then stores the result of the implementation in a produced variable.

The JavaScript function field automatically creates the structure of a predefined JavaScript function.

![Screenshot of the Run JavaScript function on web page action.](..\media\run-javascript-function-on-web-page-action.png)
