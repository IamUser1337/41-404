Solutions are mechanisms in Microsoft Power Platform for implementing [application lifecycle management](/power-platform/alm/?azure-portal=true) (ALM) for Microsoft Power Apps, Microsoft Power Automate, and Microsoft Power Virtual Agents. 

The benefits of using solutions with cloud flows are that they:

-   Act as a container to simplify the task of managing related resources (solution components such as cloud flows and apps) together as a collection.

-   Enable the transport of the collection of resources from one environment to another with straightforward export and import actions. You can fully automate these actions, which will eliminate manual deployment steps for cloud flows.

-   Provide connection references and environment variables so that solution cloud flows can be less environment dependent. These features allow for unique configurations in each environment where the solution is deployed.

-   Can be exported and stored in source control for version tracking. Using source control with solutions will support a single source of truth and will improve your ability to manage collaboration on the collection of resources that are managed by the solution.

You can add Power Automate cloud flows as a solution component along with other resources, such as Power Apps and Microsoft Dataverse table definitions. Then, solutions will act as a container for your components and will allow you to transport them from one Microsoft Power Platform environment to another. Additionally, you can export solutions and store them in source control as part of your ALM strategy.

You can only create solutions in a Microsoft Power Platform environment with Microsoft Dataverse provisioned. You will use Dataverse to track the components that you add to solutions. Dataverse doesn't need to manage your data; you can use it only for managing solutions. New Dataverse environments come with two default solutions: **Default** and **Common Data Services Default Solution**. You can also create your own new solutions, and we recommend that you create your own to contain the related components for your resources. When creating a new solution, make sure that you give it a unique name and associate it with a solution publisher. Remember, when you choose a name, it should represent all components that you plan to add, not only the cloud flows. For example, the following image shows the process of creating a solution to contain apps and flows that support **Leave Tracking**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the creation of a new solution called Leave Tracking.](../media/new-solution.png)](../media/new-solution.png#lightbox)

The solution publisher that you choose will be used to identify new components that you create in the solution. The prefix is prepended to the name of resources that you create in the solution to help uniquely identify them. While you can select one of two default publishers, we recommend that you create your own with a prefix set to something that represents your company or product that you're building. For example, the following image shows the creation of a Contoso publisher.

> [!div class="mx-imgBorder"]
> ![Screenshot of the creation of a new publisher for Contoso.](../media/new-publisher.png)

## Add cloud flows to solutions

You can create new cloud flows directly in a solution, or you can add existing flows. To add new cloud flows directly, start in the solution of your choice and then select **+ New**.

> [!div class="mx-imgBorder"]
> [![Screenshot of a new cloud flow being added to a solution.](../media/new-cloud-flow.png)](../media/new-cloud-flow.png#lightbox)

You can choose **Automated**, **Instant**, or **Scheduled**, and if you're uncertain about which one to choose, select any of them and then select **Skip** when prompted to specify trigger details. You'll be able to choose the required trigger in the flow designer.

After you've saved the flow, the flow definition will be stored in Dataverse and associated with the current solution and the built-in **Default** solution. To associate a cloud flow with multiple solutions, use the **Add existing** option; however, it's important to understand that the solution component will point to the same flow definition and that they're only references and not independent copies. If you change the flow from any solution in the environment, the change will show from all solutions that the flow is associated with. The **Default** solution is unique and allows you to view all resources in an environment, but you should only use that solution for reference. Resources that you've added to other solutions are also automatically associated with the **Default** solution for reference purposes.

If you create a new solution, you can add existing cloud flows as solution components by using the **Add existing** option. You can add existing cloud flows that are already in another solution or flows that are created outside of a Dataverse solution. When you're adding a flow that was already in another solution, the definition will already be in Dataverse, so the **Add existing** command will associate the flow as a solution component of the new solution as well.

When you add existing cloud flows that are created outside of a solution, the flow will be converted to store the flow definition in Dataverse. The flow will also be associated with the new solution. After conversion, the flow will only be listed in the solution and not in **My flows**. However, you can't convert all flows that are created outside Dataverse. If your flow doesn't show on the list of solutions, check the current [Known limitations](/power-apps/maker/data-platform/solutions-overview?azure-portal=true#known-limitations).

> [!div class="mx-imgBorder"]
> ![Screenshot of a list of solutions outside of Dataverse.](../media/outside-dataverse.png)

## Remove solution cloud flows

You can remove cloud flows that are in solutions from a solution or you can remove them from the Dataverse environment.

> [!div class="mx-imgBorder"]
> ![Screenshot of a cloud flow being removed or deleted.](../media/remove-delete.png)

- **Remove from this solution** - This option will remove the association from the current solution. The cloud flow definition isn't physically deleted. Other solutions that are associated with the cloud flow, including **Default**, will still have the cloud flow as a solution component. For example, by using this option, you could remove from one solution and add to another to reorganize your solutions.

- **Delete from this environment** - This option will physically delete the cloud flow definition from the Dataverse environment. As a result, any solution, including **Default**, will no longer include the flow as a solution component because it was deleted. This action should only be done when you no longer need the cloud flow.

In this unit, you learned about the basics of adding and removing cloud flows from solutions. While you don't need to use solutions with cloud flows, many benefits exist for using solutions to manage the collection of resources (apps, flows, and so on) that you're building. In the rest of the module, you'll learn about connection references, environment variables, and how to transport solutions between environments.
