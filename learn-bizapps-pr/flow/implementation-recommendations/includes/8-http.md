HTTP triggers and actions are considered built into Microsoft Power Platform and by default, don’t appear as connectors in the DLP policy editor. However, because of customer needs and past feedback, it is possible to manage the triggers/actions that are shown in the following image.

![Screenshot of H T T P, When a H T T P request is received, and H T T P Webhook.](../media/4-http.png)

These triggers/actions can only be managed in DLP policies that have a [schema version](https://flow.microsoft.com/blog/introducing-http-and-custom-connector-support-for-data-loss-prevention-policies//?azure-portal=true) of 2018-11-01, which is discussed in the linked blog. By using a new schema version, it allows organizations to make the decision to implement these changes. Otherwise, it's highly possible that some flows will be broken, depending on how an organization wants to classify the connectors as business or non-business.

For example, if the HTTP action was previously not managed and is being used with connectors from the **Business** data group and is then placed in
the **Non-business** data group, then any flows that are using this configuration will be suspended because of DLP violations.

By using this new schema version, DLP policies can be constructed by using either of the following tables:

- Microsoft Power Platform Management connector

- Power Apps and Power Automate PowerShell cmdlets

However, using PowerShell is the simplest path forward. Additional information about PowerApps and Power Automate PowerShell cmdlets can be found at [PowerShell support for Power Apps](/power-platform/admin/powerapps-powershell/?azure-portal=true).

After installing the prerequisite PowerShell modules, you can run the following statement, (**New-AdminDlpPolicy -DisplayName "HTTP DLP Policy" -SchemaVersion 2018-11-01**), which will create a new DLP policy that includes support for HTTP when you include a **-SchemaVersion** parameter of **2018-11-01**. After you have run the previous statement, you'll be asked to sign in by using your admin credentials.

![Screenshot of PowerShell H T T P D L P policy.](../media/5-http-dlp.png)

After the command has been run, you'll be provided a status output that includes the internal **PolicyName** and other attributes.

![Screenshot of PowerShell results showing PolicyName, Type, DisplayName, CreatedTime, CreatedBy, and other attributes.](../media/6-ps-results.png)

If you go to the [Power Automate Admin Center](https://admin.flow.microsoft.com/apiPolicies/?azure-portal=true), you'll discover that the DLP policy has been created.

> [!NOTE]
> Because an environment parameter was not specified when you
created this DLP policy, it will be applicable to the entire tenant.

After you have explored this DLP policy, you'll find that your HTTP triggers and actions are included in your default data group, which in this case is **No business data allowed**. These connectors can be
managed just like any other connectors and can be added to the **Business data only** data group.

![Screenshot of Power Automate Admin Center Data policies page with H T T P options highlighted.](../media/7-http-dlp.png)
