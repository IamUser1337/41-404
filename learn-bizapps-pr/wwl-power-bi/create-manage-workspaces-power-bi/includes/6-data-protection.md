As enterprises grow, so does their data. Often, strict requirements and regulations must be applied to ensure that this sensitive data is secure. Power BI provides a few different ways to help you accomplish this task:

-   Use Microsoft sensitivity labels to label dashboards, reports, semantic models, and dataflows by using the same taxonomy that is used to classify and protect files in Microsoft 365.

-   Add more protection measures such as encryption and watermarks when you are exporting the data.

-   Use Microsoft Cloud App Security to monitor and investigate activities in Power BI.

To continue with the module scenario, as more reports and dashboards are increasingly added to the Tailwind Traders workspace, the Sales team becomes concerned as they realize the urgency of securing their data. The team is concerned about the possibility of new users exporting data without permission. The Sales team doesn't want to roll back reports or dashboards, so they have asked you to implement comprehensive security measures that protect data access within and outside of Power BI. You can complete this task by configuring data protection labels in Power BI. 

Before you begin, ensure that you have the appropriate licensing, as shown [here](/power-bi/admin/service-security-data-protection-overview/?azure-portal=true).

## Sensitivity labels

Sensitivity labels specify which data can be exported. These labels are configured externally to Power BI, and Power BI allows you to quickly use them in your reports and dashboards. These labels allow you to define and protect content, even outside of Power BI. semantic models, dataflows, reports, and dashboards can use this mechanism, and all users in your corporation can use this feature unless exceptions have been defined.

After you have verified your ability to add labels, go to any workspace and choose an object to secure. For this example, you will add a sensitivity label to **Sales Data** by going to the workspace and, under the ellipsis (**...**), selecting **Settings**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Settings feature for the Sales Dashboard.](../media/06-exporting-excel-4-ssm.png)](../media/06-exporting-excel-4-ssm.png#lightbox)

This selection will take you to a window, where you can assign a sensitivity label to your data. For this example, the following labels have been externally configured, so you can now apply them to the data: **None**, **Personal**, **General**, **Confidential**, and **Highly confidential**. You can also go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage/?azure-portal=true) to define your own labels.

> [!div class="mx-imgBorder"]
> [![Screenshot of the sensitivity label settings.](../media/06-sensitivity-settings-1-ssm.png)](../media/06-sensitivity-settings-1-ssm.png#lightbox)

For example, if you want to assign a **Confidential** label to your **Sales Data** report, when you change this label on the **Settings** pane, it will appear as a label on the report, as shown in the following figure.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Dashboard with a sensitivity label.](../media/06-reports-dashboards-cards-6-ss.png)](../media/06-reports-dashboards-cards-6-ss.png#lightbox)

This factor is crucial when you are exporting data. Data that is exported to Microsoft Excel, Microsoft PowerPoint, and PDF files will have sensitivity labels enforced. For instance, if you wanted to export data from **Sales Data** into an Excel file, if you are an authorized user, you will see the following Excel view when you export into Excel.

> [!div class="mx-imgBorder"]
> [![Screenshot of the sensitivity label on data exported to Excel.](../media/06-dashboard-with-label-4-ssm.png)](../media/06-dashboard-with-label-4-ssm.png#lightbox)

However, if you didn't have established permissions, you would be denied access to see the data. This verification ensures that only appropriate users have access to view the data, which helps make sure that your data is secured.

For more information, see [Apply Data Sensitivity Labels in Power BI](/power-bi/collaborate-share/service-security-apply-data-sensitivity-labels).