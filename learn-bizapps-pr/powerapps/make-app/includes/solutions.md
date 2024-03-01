> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE50yts]

Solutions help you transport apps and components from one environment to another or apply a set of customizations to existing apps. A solution can contain one or more apps and other components, such as site maps, tables, processes, web resources, choices, flows, and more.

Solutions are the mechanisms for implementing application lifecycle management (ALM) in Power Apps and other Microsoft Power Platform products, such as Power Automate.

For more information, see [Overview of ALM with Microsoft Power Platform](/power-platform/alm/overview-alm/?azure-portal=true) in the Microsoft Power Platform ALM guide.

Consider the following known limitations regarding working with canvas apps, flows, and custom connectors in solutions:

- You need to create canvas app instant flows from an app that's already in a solution. The ability to add this type of flow from outside solutions is blocked.

    **Workaround for this limitation**: Remove the trigger, replace with another trigger, such as recurrence, save the flow, add it into a solution, and then change the trigger as needed.

- Canvas apps don't display in the classic solution explorer. Use the modern experience. No plans are in place for them to be added to classic solution explorer.

- Flows that have been created from solutions aren't displayed in the **Shared with me** list. You need to access them through a solution.

- Currently, the [Power Automate mobile app](/power-automate/mobile-manage-flows/?azure-portal=true) doesn't support flows that have been created in a solution.

- Currently, the **Flow action** menu in [Power Apps for mobile](/powerapps/mobile/run-powerapps-on-mobile/?azure-portal=true) and [Dynamics 365 for phones and tablets](/dynamics365/mobile-app/overview/?azure-portal=true) doesn't support flows that have been created in a solution.

- Flows in solutions don't support delegated authentication. For example, access to a flow can't be granted automatically based on having access to the SharePoint list that the flow was created from.

- Custom connectors that have been created outside solutions can't be added to solutions at this time.

- Canvas apps that are shared with everyone that goes through environment backup and environment restore operations aren't shared with everyone in the restored environment. You can share the canvas app with a security group and then the app in the restored environment are shared with that security group.

- Flows that use [connectors](/connectors/connector-reference/?azure-portal=true) and are indexed can't be added into solutions. Indexing isn't supported for solution cloud flows yet. Indexing enables the quick retrieval of those flows to display in a menu or list. Indexed connectors include:

  - Power Automate instant (button) flows

  - Power Apps

  - Microsoft Teams

  - SharePoint

  - Microsoft Dynamics 365 Customer Voice

  - Microsoft Forms

  - Legacy Dataverse connector

  - Dynamics 365

  - Excel Online

  - Microsoft Project

  - Microsoft Azure IOT Central V2

  - Project Online

    **Workarounds for this limitation**:

  - Edit the flow to remove the indexed connector triggers/actions, add it into a solution, and then change it back.

  - Create a new flow in a solution.

- Flows that have been triggered from Microsoft 365 applications, such as Excel, can't view/show cloud flows in solutions because they use indexing.

## Recommended content

For more information, see the following articles:

- [Solutions overview](/power-apps/maker/data-platform/solutions-overview/?azure-portal=true)

- [Create a solution](/power-apps/maker/data-platform/create-solution/?azure-portal=true)

- [Export solutions](/power-apps/maker/data-platform/export-solutions/?azure-portal=true)

- [Import solutions](/power-apps/maker/data-platform/import-update-export-solutions/?azure-portal=true)

- [Upgrade or update a solution](/power-apps/maker/data-platform/update-solutions/?azure-portal=true)
