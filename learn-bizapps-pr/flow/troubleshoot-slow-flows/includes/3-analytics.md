As Power Automate flow consumption increases, it's important to monitor the health of these flows. Analytics is available at the flow level and the environment level.

## Analytics at the flow level

You can access flow-level analytics from two locations. One location is from the list of flows that you have access to.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Cloud flows tab with the ellipsis button for a flow in the list selected and the Analytics option highlighted.](../media/image-14.png)](../media/image-14.png#lightbox)

The second analytics location is in the flow settings.

> [!div class="mx-imgBorder"]
> [![Screenshot of the details for a flow with the Analytics button highlighted.](../media/image-15.png)](../media/image-15.png#lightbox)

Flow-level analytics provides information such as actions, usage, and errors. Each of these areas is a Microsoft Power BI report, and the data that is presented ranges from the last 7, 14, and 30 days.

The following screenshot shows an example of the flow **Actions** analytics. It presents the total number of billable actions that have run so far.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Actions tab showing a graph of the last 30 days. The ellipsis button is selected and Sort ascending is set to AggregationDate.](../media/image-16.png)](../media/image-16.png#lightbox)

The following image shows an example of the flow **Usage** analytics. This report provides a breakdown of the total number of runs that you had in a day and how many of those runs were successful and how many failed. This report only provides numbers.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Usage tab showing graphs of Runs by day, Number of runs, and Flow runs trend.](../media/image-17.png)](../media/image-17.png#lightbox)

The **Errors** tab also provides you with a total count by day and **Error details**, such as the error types and details of that error.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Errors tab showing graphs of Errors by day, Errors by type, and the list of Error details.](../media/image-18.png)](../media/image-18.png#lightbox)

## Analytics at the environment level

Admins with the following roles and a license can view the reports in Power Automate analytics:

- **Environment admin** - Can view reports for the environments that the admin has access to.

- **Microsoft Power Platform admin** - Can view reports for all environments.

- **Dynamics 365 admin** - Can view reports for all environments.

- **Microsoft 365 Global admin** - Can view reports for all environments.

The reports provide insights into runs, usage, errors, types of flows that are created, shared flows, and details on connectors that are associated with different flow types such as automated flows, button flows, scheduled flows, approval flows, and business process flows. Each report is a Power BI report, and the data that is presented ranges from the last 7, 14, and 28 days.

> [!div class="mx-imgBorder"]
> [![Screenshot of Microsoft Power Platform admin center on the Power Automate page with Change filters selected to open the Filters dialog box.](../media/image-19.png)](../media/image-19.png#lightbox)

By default, the **Runs** report appears first. It provides a view into the daily, weekly, and monthly run data of all flows in an environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Runs tab showing graphs of daily, weekly, and monthly runs.](../media/image-20.png)](../media/image-20.png#lightbox)

The **Usage** report provides insights into the different types of flows in use, the trends, and the flow creators' names.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Usage tab showing graphs of types of flows in use, usage trend, and a list of cloud flows in use.](../media/image-21.png)](../media/image-21.png#lightbox)

The **Created** report provides insights into the types of flows that are created, creation trends, and details such as the created date and the creator's email address.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Created tab showing graphs of types of flows created, creation trend, and a list of created cloud flows.](../media/image-22.png)](../media/image-22.png#lightbox)

The **Errors** report provides insights into recurring error types and details such as the error count, creator's email address, last occurred time, and the creator's email address for each flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Errors tab showing a graph of errors by type and a list of errors by cloud flows.](../media/image-23.png)](../media/image-23.png#lightbox)

The **Shared** report provides details on the shared flows and trends in the environment.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power Automate analytics Shared tab showing graphs of types of shared flows, flows share trend, and a list of flows shared.](../media/image-25.png)](../media/image-25.png#lightbox)

The **Connectors** report provides details on connectors and their associated flows. Metrics such as the number of calls from each flow for each connector, flow runs, and the flow creator's email address are available for standard and custom connectors.

> [!div class="mx-imgBorder"]
> [![The Connectors tab showing graphs of connectors by flow runs and calls, and lists of connector usage across flows and flows that are using connectors.](../media/image-26.png)](../media/image-26.png#lightbox)
