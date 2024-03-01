
You can create an open-source custom connector and certify it to help make it available to all users. By making it open source, you ensure that your connector is published to the [Microsoft Power Platform GitHub repository](https://github.com/Microsoft/PowerPlatformConnectors/?azure-portal=true).

## Microsoft Power Platform GitHub repository

The Microsoft Power Platform GitHub repository has multiple types of connectors that can be divided in two groups: custom and certified.

Custom connectors are connectors that any user can import from the GitHub repository into an environment and then use it or make contributions to your connector for you to consider adopting. When you create a custom connector, it's only available to you and the users whom you explicitly share the connector with. Adding the custom connector to the Microsoft Power Platform GitHub repository helps make it easier for people to import the connector into their environment.

## When to certify a custom connector

For a connector to be visible in the list of official connectors, for any user of Microsoft Power Automate, Microsoft Power Apps, or Microsoft Azure Logic Apps, you need to certify the custom connector.

Many reasons exist for certifying your custom connector, but ease of use, visibility, and expanding the reach of your API are among the top reasons. Certify your custom connector if it provides access to an API that's useful to a broad audience and isn't internally focused. You don't need to host the API underlying service on Microsoft technologies. In fact, connectors are beneficial for integrating Microsoft Power Platform solutions with non-Microsoft solutions. You can certify connectors for free or with paid APIs.

Microsoft reviews certified connectors to ensure that they meet the [certification criteria](/connectors/custom-connectors/submit-certification?azure-portal=true#certification-criteria) before publishing. Two types of connector publishers are available:

- **Verified Publishers** - A key requirement with verified publishers is that you need to own the underlying service, or you need to present explicit rights to use the API and then provide a user scenario that fits well with the products.

- **Independent Publishers** - This type of publisher doesn't own the underlying service behind their connector. For example, a user of an API who isn't affiliated with the company can submit a connector for the API for certification. This type allows users in the community to partake in the Microsoft Power Platform connector ecosystem.

Initial certification and updates to the connector are free. The next unit further explains the certification process.

## When to create an open-source custom connector

Any custom connector that you build is a candidate for becoming an open source if you determine that others could benefit from using it. When you certify a connector, your first step is to make the definition open source. Then, you need to verify if an existing custom connector definition exists in the repository for the API that you're building. If you find a definition, we recommend that you contribute your changes to make that one better by submitting a pull request rather than trying to create a duplicate connector.

The following examples describe when creating an open-source custom connector is most and least optimal.

| **Optimal open-source candidate** | **Poor open-source candidate** |
| --------------------------------- | ---------------------------------|
| Connector for an API that's publicly available for anyone to use | Connector for a private API that's only available inside your company network |

Most contributions require that you agree to a Contributor License Agreement (CLA). This agreement declares that you have the right to, and actually do, grant the rights to use your contribution. For more information, see the [Contributor License Agreement](https://cla.microsoft.com/?azure-portal=true).

The GitHub repository has three main folders that contain the connectors: 

- **custom-connectors**

- **independent-publisher-connectors**

- **certified-connectors**

The **custom-connectors** folder contains fully functional connector samples that you can deploy to Microsoft Power Platform for extension and use. These samples aren't certified connectors but are created and maintained by the open-source community to offer useful scenarios or examples of connector concepts. These connectors aren't deployed to Power Apps, Power Automate, and Logic Apps by default, which makes them different from the other two folders.

The **independent-publisher-connectors** folder contains connectors that are submitted by publishers that don't own the underlying service behind their connector. These connectors are deployed and available within Microsoft Power Platform as premium connectors. Anyone can submit a new connector to this folder, add functionality to connectors in this folder, and resolve issues that are related to the connectors in this folder. The Independent Publisher Connector Community, which includes independent publishers and project coordinators, manages this folder. The Microsoft Connector Certification Team maintains the **master** branch to ensure that the connector version is identical to the one that's deployed in Microsoft Power Platform. The connector maintainers and the Microsoft Connector Certification Team maintain the **dev** branch to allow community development of the connector before the certification and deployment of a version.

The **certified-connectors** folder contains certified connectors that are already deployed and available for use, out of the box, within Microsoft Power Platform. A requirement of the Microsoft connector certification program is that the new certified connectors must be open source for community contributions. The Microsoft Connector Certification team manages the **certified-connectors** folder to ensure that, within the **master** branch, the connector version is identical to that which is deployed in Microsoft Power Platform. The connector owner and the Microsoft Connector Certification team maintain the **dev** branch to allow community development of the connector before certification and deployment of a version.

To contribute to the GitHub repository, you can start by taking your own copy (or by *creating a fork*) of the repository. The steps are explained in the [Creating a Fork](https://github.com/Microsoft/PowerPlatformConnectors?azure-portal=true#creating-a-fork) documentation. After creating a fork, you can prepare your connector for contribution by using a pull request. You can download your connector assets by using Microsoft Power Platform Connectors CLI.

## Microsoft Power Platform Connectors CLI

To work with your connector assets, download the Microsoft Power Platform Connectors CLI by using the [installation instructions for Microsoft Power Platform Connectors CLI](/connectors/custom-connectors/paconn-cli/?azure-portal=true#installing).

> [!NOTE]
> The other name for the Microsoft Power Platform Connectors CLI is `paconn`.

## Sign in by using Microsoft Power Platform Connectors CLI

Before you can download your connector files, you need to be signed in with the [Microsoft Power Platform Connectors CLI](/connectors/custom-connectors/paconn-cli/?azure-portal=true). Sign in by running the following command:

`paconn login`

This command asks you to sign in by using the device code sign-in process. Follow the prompt for the sign-in process.

## Download by using Microsoft Power Platform Connectors CLI

To prepare the necessary files to create an open-source connector, use the `paconn download` command from [Microsoft Power Platform Connectors CLI](/connectors/custom-connectors/paconn-cli/?azure-portal=true).

Download the custom connector files by running the following command:

`paconn download`

When you run this command, a device sign-in is initiated to allow paconn to access your Microsoft Power Platform environment on your behalf. After you're authenticated, paconn provides you with a list of environments to select from followed by a list of connectors to select.

If you know your environment ID and connector ID, you can use the following command-line syntax to avoid being prompted:

`paconn download -e [Microsoft Power Platform Environment GUID] -c [Connector ID]`

The download includes four files:

- **apiDefintion.swagger.json** - OpenAPI definition for your connector that includes all triggers and actions, for example.

- **apiProperties.json** - Defines policy templates and other extended connector properties that aren't part of OpenAPI specifications.

- **icon.png** - A small icon that represents the service in the designer when the connector is used.

- **settings.json** - This file is used instead of providing parameters to `paconn`.

Making your custom connector open source and then certifying it helps you get more visibility to your API. By contributing the connector definition to the open-source repository, your custom connector becomes available for others to use. When someone uses a certified connector, they're using a definition that's updated automatically when you publish updates. When using the open-source connector definition, users need to apply updates to their own copy. The rest of this module explains how you can certify your custom connector and how to manage its life cycle as you evolve it.
