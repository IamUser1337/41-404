You can use plug-ins to centralize logic that modifies or augments data. Instant plug-ins are useful because you can complete the action on demand. For example, you can have a ScheduleService instant plug-in that could use a connector to find the next available service slot from your booking service. Then, the connector can create a data row that’s related to the requestor to track the booking. 

Automated plug-ins are good for modifying data or adding related data rows after you add the primary data row to Dataverse. A significant advantage of automated plug-ins is that any data changes that the plug-ins make are part of the original transaction, and the system completes or rolls back all changes. For example, consider a scenario where you create a Project data row, and then a plug-in that ran when you created the row creates some initial tasks that are related to the project. If one of those tasks is invalid and fails to create, the system would roll back the project and any tasks that did create.

## Change data before it's saved

The **Change data before it’s saved** option only applies to automated plug-ins that run on created or updated events. In both cases, you can set up your plug-in to run during pre-operation, which gives you an opportunity to modify the data in the row that you’re creating or updating before you save the data. This option is beneficial in scenarios where you want to set some default values. Additionally, you can use conditional Power Fx logic to make the defaults depend on other data on the row that you’re modifying.

You need to run your plug-in on pre-operation and use the set() function to modify the data columns. This approach ensures that your changes are included when you save the data row rather than being done as a separate update, which could cause an infinite loop or possibly trigger unwanted automations to run because of the separate update.

The following example shows using the set() function to modify the budget column on the project row that you’re creating.

```
Set(contoso_budget,1000)
```

You can only use this approach to change data on the row that triggers your plug-in. You can't create related data in the pre-operation stage because no primary row is available for you to attach the related data to.

## Create related data rows

Another common scenario is when you want to create related data to a primary data row. You can accomplish this task by using instant and automated plug-ins. To do so, you can use the collect() function to add the data. For example, the following function automatically adds the creator of the project as the initial team member.

```
Collect([@'Team Members'],{Name: "David So",'Team Project': ThisRecord })
```

In the preceding example, ThisRecord is the project row that’s passed in on an instant plug-in that’s set up with a scope of entity for the project table, or it’s passed in on an automated plug-in on Create of the project table.

In some scenarios, you need to use the patch() function instead of the collect() function. For example, you would use the patch() function when you’re working with the Regarding column in the Tasks table to allow the system to properly set the Regarding column. The reason is because the Regarding column is polymorphic and can point to many different table row types. The following example shows a plug-in that’s built to run on creation of a project to add some initial tasks that every project has.

```
Patch([@Tasks], Collect([@Tasks], { Subject : "Review Project"} ),{ Regarding: ThisRecord });
Patch([@Tasks], Collect([@Tasks], { Subject : "Schedule Project Launch"} ),{ Regarding: ThisRecord });
Patch([@Tasks], Collect([@Tasks], { Subject : "Assign Project Lead"} ),{ Regarding: ThisRecord });
```

In the preceding example, the patch() function is combined with the collect() function to update the Regarding column.

## Find and remove related data

Another common scenario is conditionally removing related data. For example, you could create an instant plug-in called Cancel Project. This plug-in would have an input parameter of type EntityReference for the project that you’re canceling. Then, the plug-in could update the project row to indicate that it’s canceled and then find and remove open work items so that no one can work on the canceled project. The following logic shows the expression for finding all work items that are related to the project, and it shows how you can use ForAll to loop through and call Remove for each work item.

```
ForAll(Filter([@'Work Items'], 'Team Project'.'Team Project' = Project.'Team Project'),  Remove([@'Work Items'], ThisRecord))
```
