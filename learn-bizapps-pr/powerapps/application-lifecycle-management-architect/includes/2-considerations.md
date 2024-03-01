Solution architects need to define the strategy for application lifecycle management (ALM) on the project. This task is part of the process of helping the organization establish proper governance for the solution.

## Environment strategy

An environment is a container that stores, manages, and shares your business data, apps, flows, connections, and other assets, along with permissions to allow organization members to use the resources.

An environment serves as a container to separate apps that might have different roles, security requirements, or target audiences. How you choose to use environments depends on your organization and the apps that you're trying to build, for example:

- You can choose to build your apps only in a single environment.
- You might create separate environments that group the test and production versions of your apps.
- You might create separate environments that correspond to specific teams or departments in your company, each containing the relevant data and apps for each audience.
- You might create separate environments for different global branches of your company.

Developing an environment strategy means configuring environments and other layers of data security in a way that supports productive development in your organization while simultaneously securing and organizing resources. A strategy to manage environment provisioning and access, and controlling resources within them, is important to:

- Secure data and access.
- Understand how to use the default environment correctly.
- Manage the correct number of environments to avoid sprawl and conserve capacity.
- Facilitate application lifecycle management (ALM).
- Organize resources in logical partitions.
- Support operations (and helpdesk) in identifying apps that are in production by having them in dedicated environments.
- Ensure that data is being stored and transmitted in acceptable geographic regions (for performance and compliance reasons).
- Ensure isolation of applications that are being developed.

> [![Diagram showing an example of environment strategy.](../media/2-environment-strategy.png)](../media/2-environment-strategy.png#lightbox)

The following types of environments are available in Microsoft Power Platform:

- **Sandbox** - A sandbox environment is any non-production environment of Dataverse. Isolated from production, a sandbox environment is the place to safely develop and test application changes with low risk.
- **Production** - The environment where apps and other software are put into operation for their intended use.
- **Community (developer)** - The Power Apps Community Plan gives a user access to Power Apps premium functionality, Dataverse, and Microsoft Power Automate for individual use only. This environment is primarily meant for learning purposes. A developer environment is a single-user environment and can't be used to run or share apps. A Community Plan environment can participate in the Azure DevOps pipeline.
- **Default** - A single default environment is automatically created for each tenant and shared by all users in that tenant. The default environment is used by Microsoft 365 services.
- **Trial** - Trial environments are for trying new features or to perform proof of concepts. Trial environments are automatically deleted after 30 days.

> [!IMPORTANT]
> The solution architect needs to define how many environments are required, their purposes, and the dependencies between environments. At a minimum, a healthy ALM practice should include using a test environment prior to deploying anything to the production environment. This practice ensures that you have a place to test your app, but it also ensures that the deployment can be tested.

For more information, see [environments](/power-platform/admin/environments-overview/?azure-portal=true) and [environment strategy](/power-platform/guidance/adoption/environment-strategy/?azure-portal=true).

## Handle solutions and other non-solution aware code and components

Microsoft Power Platform projects consist of components that can be packaged inside solutions in environments and components that cannot be added to solutions such as components deployed in Azure, configuration data, and Power BI reports. The ALM plan must consider how to handle these non-solution aware components.

The solution architect needs to decide if application lifecycle management will be managed by using solutions or by using source code control. Traditionally, Microsoft Power Platform projects have been more environment-centric, but many are now moving toward being source control-centric.

If you use an environment-centric approach, then:

- The dev environment is the master copy of all changes.
- Changes are promoted directly from **dev > test > production**.

If you use a source control-centric approach, then:

- Source control is the master.
- The dev environment is re-created from source control (this process can be automated and repeatable).
- Changes from the dev environment are checked into source control.

> [![Diagram that shows a source-centric approach.](../media/2-source-centric.png)](../media/2-source-centric.png#lightbox)

A source control-centric approach encourages you to have a definitive master and the ability to re-create development environments for any tracked version. Currently, Microsoft is encouraging and building tooling to support source control-centric ALM.

> [!NOTE]
> Ideally, all environments other than production should be *throw away*, in other words, the dev and test environments can be deleted and re-created without experiencing loss.

Using a source control-centric approach will enable an Azure DevOps approach with build and release pipelines. Using an environment-centric approach means that you need to define the workflow for app makers and developers. The solution architect will need to define how and who will promote the app through the environments from development to production.

The solution architect will also need to define how to configure each environment and look for ways to make it easier.

## Team working

Compared to traditional app development, Microsoft Power Apps projects differ in two key areas:

- How various members of the project team work together to create the solution
- Development methodology

Power Apps is a platform that benefits professional developers and citizen developers. In a traditional development environment, only professional developers could be involved with the actual making of an app. With Power Apps, everyone has the power to build the apps that they need by using advanced functionality that was previously available only to professional developers. Power Apps democratizes the custom business app building experience by enabling users to build feature-rich, custom business apps without writing code.

![Diagram that shows the develop ecosystem.](../media/2-ecosystem.png)

With Power Apps, you can quickly create a usable version of your app because Power Apps provides a WYSIWYG development experience. You can experience the actual working app early in the development process, and if new requirements arise, you can add new features to the next version.

> [![Diagram of Power Apps development approach.](../media/2-agile.png)](../media/2-agile.png#lightbox)

Issues with customizing and developing components within Microsoft Power Platform include:

- Microsoft Power Platform doesn't support versioning of components (except for canvas apps).
- Users can't work on the same Microsoft Power Platform component simultaneously.
- Model-driven apps have multiple components, each with their own editors, allowing work to be divided between makers. Conversely, canvas apps have only one editor and only one person can work on an app at any one time. By using canvas components, you can allow multiple makers to work on the same app simultaneously.

Solution architects should establish the workflow for how app builders will make changes and promote them. Proactive communication and work assignments should be managed to minimize conflicts between makers.

You can minimize clashes between makers by creating an individual environment for each maker. Individual maker environments offer isolation and tracking but require extra effort to merge work and resolve conflicts. A shared maker environment can be less complex, but it doesn't offer isolation between app builders and lacks detail in its tracking of changes.

## Source control

Though you are using an environment-centric approach, you will still need to decide where the master copy of the solutions and code will live.

Solution-aware developer code assets (such as plug-ins, PCF code components, and form scripts (transpiled from TypeScript)) should be "built" on a build environment and not the developer's desktop. After being built, the assets should be deployed to an environment that the master solution will be exported from or built into a solution that will be installed.

## Tools

Microsoft provides several tools and apps that you can use with ALM in Microsoft Power Platform:

- **Microsoft Power Platform admin center** - Provides a unified portal for administrators to create and manage environments.
- **Power Apps build tools** - Automate common build and deployment tasks that are related to Power Apps by using Azure DevOps. 
- **GitHub** - Popular example of a version control system.
- **Configuration Migration tool** - Enables you to move configuration and/or reference data across environments.
- **Package Deployer** - Lets you deploy packages of assets to Dataverse instances. Packages can consist of solution files and flat files, custom code, HTML files, and data.
- **Solution Packager** - A tool that can unpack a compressed solution file into multiple XML files and other files so that they can be easily managed by a source control system.
- **Microsoft Power Apps CLI** - A simple command-line interface that empowers developers to create code components.
- **Package deployment PowerShell module** - Used to deploy packages to the Dataverse environment.
- **Power Apps checker PowerShell module** - Interacts with the Power Apps checker service so that you can run static analysis jobs and download the results.

> [!NOTE]
> GitHub actions for Microsoft Power Platform are currently in preview.
