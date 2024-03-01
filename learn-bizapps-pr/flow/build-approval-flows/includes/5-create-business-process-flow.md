This unit shows how to create a business process flow by using Microsoft Power Automate.

For more about how to create a mobile task flow, see [Create a mobile task flow](/dynamics365/customer-engagement/customize/create-mobile-task-flow?azure-portal=true).

When a user starts a business process flow, the process bar at the top of the page shows the stages and steps of the process.

![Screenshot of stages in a business process flow, steps in the active stage, and the Next Step button highlighted.](../media/business-process-stages.png)

## Prerequisites

- To create business process flows, you need a Power Apps or Power Automate per user license.

- Access to [Power Automate](https://flow.microsoft.com/?azure-portal=true).

- An [environment](/power-platform/admin/environments-overview/?azure-portal=true) with a [Microsoft Dataverse database](/power-platform/admin/create-database/?azure-portal=true). (Applicable only for work or school accounts).

- Experience with creating a business process flow.

- A table the business process flow is associated with. If the business process flow isn't related to an existing table, create a new table before you create the flow.

> [!TIP]
> When you create a business process flow definition, you can define who has privileges to create, read, update, or delete instances of the business process flow. For example, for service-related processes, you might give customer service reps full access to change the business process flow instance. But you might give sales reps just read-only access to the instance, so that they can monitor post-sales activities for their customers. To set security for a business process flow definition that you create, select **Enable Security Roles** on the action bar.

## Create a business process flow

> [!IMPORTANT]
> As of August 2022, you can no longer create or manage business process flows from Power Automate outside of the solution explorer. Business process flows and instances continue to be supported through the solution explorer, Power Apps, and Dataverse table views.

1. Launch Power Automate and sign in using your organizational account.

1. In the left pane, select **Solutions**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of Solutions.](../media/select-solution.svg)

1. You can either select an existing **Solution** or create a new one.

1. Inside the solution select **+ New**, **Automation**, **Process** and then **Business process flow**.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of new Business process flow.](../media/business-process-flow.svg)

1. In the **Build a business process flow** pane, fill in the required fields:

   - **Display name**: The display name of the process doesn't have to be unique, but it should be meaningful for people who must choose a process. You can change this name later.

   - **Name**: A unique name based on the display name. You can change the name when you create the process, but you can't change it after the process is created. Power Automate can generate this for you.

   - **Table**: Select the Microsoft Dataverse Table on which to base the process.

   The Table that you select affects the fields that are available for steps that can be added to the first stage of the process flow. If you can't find the table that you want, make sure that the **Business process flows (fields will be created)** option is set for the table in the table definition. You can't change the table after you save the process.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of new Business process flow details.](../media/details.SVg)

1. Select **Create**.

1. The business process flow designer is started. The designer page has three sections:

   - On the left, a single stage named *Account New Stage* was created for you.

   - Beneath this stage is the mini map, which lets you see the whole process or quickly go to a part of the process.

   - On the right are components that you can drag to the designer. You can also set properties to create a business process flow.

   > [!div class="mx-imgBorder"]
   > ![Screenshot of PowerApps business process flow designer.](../media/designer-main-elements.svg)

1. Add stages so that users can proceed from one business stage to another in the process:

   1. Drag the **Stage** component from the **Components** tab to the plus sign (**+**) in the designer.

      > [!div class="mx-imgBorder"]
      > ![Screenshot of dragging a business process stage to the plus sign.](../media/drag-business-process-stage.svg)

   1. Select the stage, and then, on the **Properties** tab on the right, set the properties:

      1. Enter a Step Name.

      1. Optional: Select a category for the stage (for example, **Qualify** or **Develop**). This category appears as a chevron on the process bar.

      1. When you finish setting the properties, select **Apply**.

1. Add steps to each stage:

   > [!TIP]
   > To see the steps in a stage, select **Details** in the lower-right corner of the stage.

   1. Drag the **Data Step** component from the **Components** tab to the stage.

      > [!div class="mx-imgBorder"]
      > ![Screenshot of adding a step to a stage in a business process.](../media/add-step-stage-business-process.svg)

   1. Select the step, and then, on the **Properties** tab, set the properties:

      1. Enter a Step Name.

      1. If users should be able to enter data to finish a step, select the appropriate field in the drop-down list.

      1. If users must fill in the selected field to finish the step before they can proceed to the next stage of the process, select **Required**.

      1. When you finish, select **Apply**.

1. Add a Condition to the process:

   1. Drag the **Condition** component from the **Components** tab to the plus sign (**+**) between two stages.

      > [!div class="mx-imgBorder"]
      > ![Screenshot of adding a condition to a business process flow.](../media/add-condition-business-process-flow.svg)

   1. Select the condition, and then, on the **Properties** tab, set the properties. When you finish, select **Apply**.

1. Add a workflow to the process:

   1. Drag the **Workflow** component from the **Components** tab to either a specific stage or the **Global Workflow** item:

      - Drag the **Workflow** component to a specific stage if the workflow should be triggered when the process enters or exits that stage. The **Workflow** component must be based on the same primary table as the stage.

      - Drag the **Workflow** component to the **Global Workflow** item if the workflow should be triggered when the process is activated or archived (that is, when the status changes to **Completed** or **Abandoned**). The **Workflow** component must be based on the same primary table as the process.

   1. Select the Workflow, and then, on the **Properties** tab, set the properties:

      1. Enter a display name.

      1. Select when the workflow should be triggered.

      1. Search for an existing on-demand active workflow that matches the stage table or create a workflow by selecting **New**.

      1. When you finish, select **Apply**.

1. To validate the business process flow, select **Validate** on the action bar.

1. To save the process as a draft while you continue to work on it, select **Save** on the action bar.

   > [!IMPORTANT]
   > No one can use a process while it's a draft.

1. To activate the process and make it available to your team, select **Activate** on the action bar.

1. To define who has privileges to create, read, update, or delete the business process flow instance, select **Edit Security Roles** on the action bar. For example, for service-related processes, you might give customer service reps full access to change the business process flow instance. But you might give sales reps read-only access to the instance, so that they can monitor post-sales activities for their customers.

   1. In the **Security Roles** pane, select the name of a role to open the details page for that role.

   1. On the **Business Process Flows** tab, select options to assign the role appropriate privileges for the business process flow.

      > [!NOTE]
      > By default, the System Administrator and System Customizer security roles have access to new business process flows.

      > [!div class="mx-imgBorder"]
      > ![Screenshot of the assign privileges to a business process flow screen.](../media/assign-privileges.png)

   1. Select **Save**.

> [!TIP]
> Keep these tips in mind as you work on your business process flow in the designer:
>
> - To take a snapshot of everything in the business process flow designer, select **Snapshot** on the action bar. This option is useful if you want to share and get comments about the process from a team member.
>
> - Use the mini map to quickly go to different parts of the process. This option is useful when you have a complicated process that scrolls off the screen.
>
> - To add a description of the business process, select the arrow beside the process name in the upper-left corner of the page. You can enter up to 2,000 characters in the description field.

## Edit a business process flow

You can edit the business process flow after it's created.

1. On the Power Automate main page, select **Solutions** in the left pane. Select your solution.

1. In the solution, select **Processes**, select your process and then select **Edit**.

Keep the following points in mind when you edit the stages of a business process flow:

- Business process flows can have up to 30 stages.

- You can add or change the following properties of a stage:

  - **Name**: You can change the stage name after you create the stage.

  - **Table**: You can change the table for any stage except the first one.

  - **Stage Category**: A category lets you group stages by the type of action. It's useful for reports that will group records by the stage that they're in. The options for the stage category come from the Stage Category global choice set. You can add more choices to this global choice set and change the labels of existing choices. You can also delete choices, but we recommend that you keep the existing choices. If you delete a choice, you can't add it back later. If you don't want a choice to be used, change the label to *Don't use*.

  - **Relationship**: Enter a relationship when the preceding stage in the process is based on a different table than the current stage. For the current stage, select **Select relationships**, and then specify the relationship that should be used when the flow moves between the two stages. We recommend that you specify relationships because they provide the following benefits:

    - Attribute maps are often defined for relationships. These attribute maps automatically carry over data between records. Therefore, they help minimize the amount of data entry required.

    - When you select **Next Stage** on the process bar for a record, any records that use the relationship are listed in the process flow. Therefore, the reuse of records in the process is promoted. In addition, you can use workflows to automate the creation of records. Users then just have to select the workflow instead of creating a record. Therefore, the process is streamlined.

  - **Set Order Process Flow**: If you have more than one business process flow for a table, you must specify which process is automatically assigned to new records. On the action bar, select **Order Process Flow**. For new records or records that don't already have a process flow associated with them, the first business process flow to which a user has access is used.

  - **Enable Security Roles**: A user's access to a business process flow depends on the privileges defined for the business process flow in the security role assigned to the user. By default, only the System Administrator and System Customizer security roles can view a new business process flow.
