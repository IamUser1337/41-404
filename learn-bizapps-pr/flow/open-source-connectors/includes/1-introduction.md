
You can create an open-source custom connector and certify it to help make it easily available to all users. By making it open source, you ensure that your connector will be published to the [Microsoft Power Platform GitHub repository](https://github.com/Microsoft/PowerPlatformConnectors/?azure-portal=true). From the repository, any user can import your custom connector definition into an environment and then use it or make contributions to your connector for you to consider adopting. When you create a custom connector, it's only available to you and the users whom you explicitly share the connector with. For a connector to be visible in the list of official connectors for any user of Microsoft Power Automate, Microsoft Power Apps, or Microsoft Azure Logic Apps, it needs to be certified.

## When to certify a custom connector

Many reasons exist for certifying your custom connector, but ease of use, visibility, and expanding the reach of your API are among the top reasons. Certify your custom connector if it provides access to an API that is useful to a broad audience and isn't internally focused. You don't have to host the API underlying service on Microsoft technologies. In fact, connectors are beneficial for integrating Microsoft Power Platform solutions with non-Microsoft solutions. You can certify connectors for free or with paid APIs.

Certified connectors are reviewed to ensure that they meet the [certification criteria](/connectors/custom-connectors/submit-certification?azure-portal=true#certification-criteria) prior to publishing. There are two types of connector publishers verified and independent.

- **Verified Publishers** - A key requirement is that you must own the underlying service, or you must present explicit rights to use the API and then provide a user scenario that fits well with the products. 

- **Independent Publishers** - Doesn't own the underlying service behind their connector. For example, a user of an API who isn't affiliated with the company can submit a connector for the API for certification. This type allows those in the community to be able to partake in the Power Platform connector ecosystem.

Initial certification and updates to the connector are free. The next unit will further explain the certification process.

## When to create an open-source custom connector

Any custom connector that you build is a candidate for becoming an open source if you determine that others could benefit from using it. When you certify a connector, your first step is to make the definition open source. First, verify if an existing custom connector definition exists in the repository for the API that you're building. If you find a definition, we recommend that you contribute your changes to make that one better by submitting a pull request rather than trying to create a duplicate connector.

The following are examples of when creating an open-source custom connector is most and least optimal.

| **Optimal open-source candidate** | **Poor open-source candidate** |
| --------------------------------- | ---------------------------------|
| Connector for an API that is publicly available for anyone to use | Connector for a private API that is only available inside your company network |

Most contributions require that you agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant the rights to use your contribution. For more information, see the [Contributor License Agreement](https://cla.microsoft.com/?azure-portal=true).

The GitHub repository has three main folders that contain the connectors: **custom-connectors**, **independent-publisher-connectors** and **certified-connectors**.

The **custom-connectors** folder contains fully functional connector samples that can be deployed to Microsoft Power Platform for extension and use. These samples might not be certified connectors but are created and maintained by the open-source community to offer useful scenarios or examples of connector concepts.

The **independent-publisher-connectors** folder contains connectors that are submitted by publishers that don't own the underlying service behind their connector. These connectors are deployed and available within the Power Platform as premium connectors. Anyone can submit a new connector to this folder, add functionality to connectors in this folder, and resolve issues related to the connectors in this folder. The folder is managed by the Independent Publisher Connector Community, which includes Independent Publishers and Project Coordinators. The master branch is maintained by the Microsoft Connector Certification Team, who ensures that the connector version is identical to that deployed in the Power Platform. The dev branch is maintained by the connector maintainer(s) and the Microsoft Connector Certification Team to allow community development of the connector prior to certification and deployment of a version.

The **certified-connectors** folder contains certified connectors that are already deployed and available for use, out of the box, within Microsoft Power Platform. A requirement of the Microsoft connector certification program is that new certified connectors must be open source for community contributions. The Microsoft Connector Certification team manages the **certified-connectors** folder to ensure that, within the **master** branch, the connector version is identical to that which is deployed in Microsoft Power Platform. The **dev** branch is maintained by the connector owner and the Microsoft Connector Certification team to allow community development of the connector prior to certification and deployment of a version.

To contribute to the GitHub repository, you'll start by taking your own copy (or *creating a fork*) of the repository. The steps are explained in the [Creating a Fork](https://github.com/Microsoft/PowerPlatformConnectors?azure-portal=true#creating-a-fork) documentation. After you've created a fork, you're ready to prepare your connector for contribution by using a pull request. You can download your connector assets by using Microsoft Power Platform Connector CLI.

## Download by using Microsoft Power Platform Connector CLI

To prepare the necessary files to create an open-source connector, use the paconn download command from [Microsoft Power Platform Connectors CLI](/connectors/custom-connectors/paconn-cli/?azure-portal=true).

Download the custom connector files by running the following command:

`paconn download`

When you run this command, it will go through a device sign in to allow paconn to access your Microsoft Power Platform environment on your behalf. After you've been authenticated, paconn will provide you with a list of environments to select from followed by a list of connectors to select.

If you know your environment ID and connector ID, you can use the following command-line syntax to avoid being prompted:

`paconn download -e [Microsoft Power Platform Environment GUID] -c [Connector ID]`

The download includes four files:

- **apiDefintion.swagger.json** - OpenAPI definition for your connector that includes, for example, all triggers and actions.

- **apiProperties.json** - Defines policy templates and other extended connector properties that aren't part of OpenAPI specifications.

- **icon.png** - A small icon that is used to represent the service in the designer when the connector is used.

- **settings.json** - Used instead of providing parameters to paconn.

Making your custom connector open source and then certifying it will help you get more visibility to your API. By contributing the connector definition to the open-source repository, your custom connector becomes available for others to use. When someone uses a certified connector, they're using a definition that is updated automatically when you publish updates. When using the open-source connector definition, users will need to apply updates to their own copy. The rest of this module will examine how to certify your custom connector and how to manage its life cycle as you evolve it.
