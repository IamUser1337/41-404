Two common ways that you can use Monitor as part of your regular
app-building process are:

- **Reactive** - You are aware of a problem and need help with identifying the root cause. For example, if someone who is using your app
    reported an error, you can use Monitor to pinpoint the cause.
    Typically, you will have a good idea of where an error
    occurs in an app, and you can use Monitor to observe events for a specific action in the app.

- **Proactive** - As part of your normal app-building process,
    before you release your app to users, you can use Monitor to
    identify possible problems. When performing proactive testing, you will most
    often run the app while Monitor captures events. By
    reviewing the event log, you can look for long response times, other anomalies, or errors. Problems
    that are identified proactively at the build stage will lead to fewer problems
    being seen by users in production and will result in the perception of a
    higher-quality app.

The rest of this module will examine how to identify and resolve
common problems by using Monitor.

Regardless of which approach that you use, we recommend that you start
your capture with an empty event log. You can accomplish this task by
selecting the **Clear data** button in Monitor before starting your actions
in the app that you are testing.

:::image type="content" source="../media/clear-data.png" alt-text="![Screenshot showing the Clear data button highlighted.]":::

## Use meaningful control names

The control names that are included in the captured events are key correlations of
the event regarding where it happened in your app. Using good names for
controls can help make it easier for you to work with the event data. Consider
the following example that compares default-generated names to
more meaningful, recommended ones. As shown, it would be
easier to identify what control was involved in the activity when
meaningful names are used.

:::image type="content" source="../media/control-names.png" alt-text="![Screenshot showing generic names versus meaningful names and how they can make the data more useful.]":::

## Find similar events

When you are working to identify the source of a problem, a common task that you might complete is
finding other occurrences that might be related. Monitor helps make that easier for you by
offering two approaches to filter the event data that has been captured.
You can use the global filter option to search across all columns
in the event log data. You can find the global filter in the upper-right
corner of Monitor.

:::image type="content" source="../media/filter-tool.png" alt-text="![Screenshot of the Filter option in Monitor.]":::

This filter is beneficial to use when you don't have a specific field that you're
looking for the data in. For example, you want to look broadly across
all columns for something that matches a pattern, such as the name of a
control or a connector action.

Each column also offers the ability for you to filter and provide more data-type
specific filtering options. You can activate the column filter by
selecting the arrow next to each column name and then selecting **Filter by**.

:::image type="content" source="../media/filter-column.png" alt-text="![Screenshot showing the Filter by option.]":::

You can also apply the **Filter by** option on multiple columns concurrently, giving
you the ability to create criteria that includes more than one column with
your requested values. When you have filters on multiple columns,
each event must qualify for all column filters to show.

Using the filter capabilities can be helpful if you have captured numerous
events and want to isolate specific problems.

## Identify and resolve errors

Commonly, errors are found because they presented an error message
to the user or triggered some error handling logic in the app.
Monitor is useful in these cases because it has more detailed
information about the specific error when the error involves a
connector. As app error handling becomes more sophisticated, the error can also be absorbed by error handling logic, and the only way that you can view it is by looking at the captured data. This situation is a good
example of where proactive app monitoring can catch errors that
you weren't expecting or didn't know were occurring.

The simplest way to identify an error in the event data log is to look
at the result column where it contains the word **Error** instead of
**Success**.

:::image type="content" source="../media/event-log.png" alt-text="![Screenshot showing the error in the event log.]":::

Another way to identify errors is from a red circle indicator that will be located at the beginning of the lines that
contain errors.

Often, the status column will contain a detailed HTTP status code that
will give you a more specific error category. The resulting information
usually contains a text summary of the status code. For more information about the different HTTP status code values, see [HttpStatusCode Enum](/dotnet/api/system.net.httpstatuscode/?azure-portal=true).

To work toward resolving errors, your best information will come from the
**Formula**, **Request**, and **Response** tabs in the **Details** area, which is shown when
you select one of the errors. The formula is useful to correlate to what
caused the error in the app, but the request and response will provide
underlying details.

The most common cause of errors is bad or missing data when you are using a
connector. You can review the request to determine what was sent to the
connector that caused the error.

While contents of the request can vary from connector to connector,
the two most common factors to look for in the request are the URL and
the body.

:::image type="content" source="../media/request-screen.png" alt-text="![Screenshot showing the Request tab, highlighting the URL and the body property.]":::

In most cases, for connector actions that make changes to data, you will
find the most valuable information in the body. Generally, you will
look for bad or missing data from what you expected would be sent to
the connector for the request. Comparing the request body to the
connector action API documentation can also highlight problems.

For query type actions, the URL typically would contain other useful
information in the query string.

The **Response** tab contains the data that is returned from the connector. While
each connector can have a uniquely defined response structure, you can find many
errors by looking at hints from scanning the response
message. In the following example, a business rule blocked the request
to create a test contact record and an error message was included in the
response.

:::image type="content" source="../media/response-message.png" alt-text="![Screenshot highlighting the error message in the response data.]":::

While the contents of the request and response might seem overly complex,
if you do a quick scan of them, it can often result in hints that will help you resolve the
problem. If the hints aren't helpful, you can provide these details to
the connector developer, or support can help them understand how you were
using the connector.

## Identify and resolve slow actions

While you might have a user who tells you what specifically is slow
in your app, the **Duration** column is another good indicator. You can use
a filter on the **Duration** column after you've run the application so that
you can focus on only the slow actions. The value for duration is
tracked in milliseconds (ms). In the following example, you would look for any event log
entry that took longer than one second.

:::image type="content" source="../media/column-filter.png" alt-text="![Screenshot showing the column filter for duration greater than one second.]":::

If your app conducts numerous data loading processes during startup,
you need to make sure that the monitor is running and that you have selected the **Run OnStart** logic.

:::image type="content" source="../media/run-onstart.png" alt-text="![Screenshot showing the Run OnStart option in Power Apps Studio.]":::

The most common way to resolve slow actions is to reduce the amount of
work that is done by the action or the amount of data that is returned
from the action. By analyzing the request, you might be able to identify
whether your criteria have been properly passed and if you could provide
more criteria to reduce the work. Also, you can
examine the response to identify if more data is being returned
than you need. Some connectors can automatically identify and return the
proper data while others require you to specify options on the request
to return only the data that's relevant.

## Identify and resolve delegation problems

[Delegation](/power-apps/maker/canvas-apps/delegation-overview/?azure-portal=true)
issues occur when you compose a query that contains criteria that can't
be resolved completely and implemented remotely by the connector service.
When this situation occurs, the app sends only part of the criteria to the
connector to return more records than necessary and to postprocess
the results from the connector in the app. The number of records that
can be pulled back and postprocessed is limited by an app setting and
defaults to 500. If more eligible records are available from the
connector than the specified limit, the results will be truncated, and
you might have inaccurate results in your app.

In many cases, **App checker** in Power Apps Studio will identify the
delegation problem, and you can resolve the problem without Monitor.
Monitor will also flag these events and provide more detail. If you
can't identify the problem with the information that **App checker** provided,
review the request that was sent to the connector. Specifically, you should review
the query criteria data that is missing, which can help you understand
what you can't send to the connector as delegable criteria.

Often, you can resolve delegation problems by rewriting the
formula to not include dynamic data calculations in the criteria that are sent to
the connector. Different connectors support different functions for
delegation, and you might find that what worked for one connector doesn't work
for another. You can use Monitor to verify that the formula will return the
correct results.

This unit reviewed some common errors that you might
try to resolve by using the Monitor tool. Monitor should be your go-to tool
when you need more detailed information about what is happening in your
application. By running Monitor regularly, you will be able to quickly identify
abnormal behaviors and issues in your application.
