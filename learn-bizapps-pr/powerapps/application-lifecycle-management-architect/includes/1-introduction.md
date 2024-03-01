The application life cycle is the cyclical software development process that involves these areas: plan and track, develop, build and test, deploy, operate, monitor, and learn from discovery.

![Diagram of application lifecycle management.](../media/1-alm.png)

This module explains how you can define your environment structure, compose your solutions, develop your application lifecycle management (ALM) strategy, and then use the build and release pipelines in Microsoft Azure Pipelines, one of the services of Azure DevOps.

## Application lifecycle management with Microsoft Power Platform

Microsoft uses solutions to package apps and customizations and export from one Microsoft Dataverse environment as a file and then import that solution package file into another Dataverse environment. The solution packaging supports different scenarios from simple changes to fully automated release management. Microsoft uses the same method for packaging its own apps and updates.

Microsoft also provides tools for you to export solutions from a development Dataverse environment and then import them to test and production environments by using Azure DevOps.

The following concepts are important for understanding ALM by using Microsoft Power Platform:

- Solutions are the mechanisms for implementing ALM; you would use them to distribute components across environments through export and import. A component represents something that you can potentially customize. Anything that can be included in a solution is a component, such as site maps, apps, entities, fields, charts, or plug-ins.
- Dataverse stores all artifacts, including solutions.
- Source control should be your source of truth for storing and collaborating on your components.

## Microsoft's vision

Microsoft Power Platform vision for ALM is to enable apps and customizations to be deployed through automated processes: 

- **Quick Start** - Enable app builders to be set up with an environment with the latest build, connect to source control, and make a change quickly.
- **Build** - Simplify tooling, consolidate portals, and speed up inner loop.
- **Deploy** - Enable an automated, repeatable (predictable) deployment methodology.
- **Manage** - Invest in other environment management capabilities to offer more flexibility for app builders to use and dispose preconfigured environments as needed.
- **Monitor** - Application telemetry and feedback loop by design.

Solution architects should understand the vision and journey that Microsoft is on to shape how ALM is done for Microsoft Power Platform projects.  As this journey evolves, solution architects should continue to shape their own plans to apply the capabilities that are provided by the platform and tools.

## Solution architect role

Solution architects for Microsoft Power Platform need to define the environment strategy and application lifecycle management for transporting work from development to test to production.

The solution architect should:

- Lead the establishment of an application lifecycle management (ALM) plan.
- Evaluate and determine the amount and sophistication of the ALM that is appropriate for the project.
- Work with the various teams to support their efforts in implementing the plan.
