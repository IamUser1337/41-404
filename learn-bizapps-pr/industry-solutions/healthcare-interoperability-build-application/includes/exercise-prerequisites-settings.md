After you create the new model-driven app, you need to set up connectivity from virtual health data tables to the Azure Health Data Services FHIR server. This process involves providing connectivity details in the Data integration toolkit by using the Integration Settings feature.

Before setting up the Integration Settings feature, if not already done, you need to set up some dependencies. You need an instance of Azure Health Data Services workspace with FHIR services deployed. Then, you can connect virtual health data tables to this service.

Next, you need to set up the tools for posting data to the **FHIR service** and the **Dataverse Healthcare APIs**. Virtual health data tables are dependent on patient records already being synced between the FHIR service and Dataverse, and Dataverse Healthcare APIs is the mechanism that pulls FHIR-based data into Dataverse.

In the following steps, you’ll complete these tasks:
- Set up prerequisites for Microsoft Cloud for Healthcare and related services. 
- Set up the Azure Health Data Services workspace.
- Set up access to Azure Health Data Services and then set up application registration.
- Validate connectivity by using Postman and then set up a Postman workspace.
- Set up Dataverse Healthcare APIs.
- Set up the virtual health data tables settings and then update integration settings.

## Prerequisites
To complete the steps in this exercise, you need to meet the following prerequisites:

-   Microsoft Cloud for Healthcare Trial with Data integration toolkit installed

    For more information, see [Microsoft Cloud for Healthcare training environment preparation](/training/modules/training-environment-preparation-healthcare/?azure-portal=true).

-   System Administrator rights are granted for the user on a Microsoft Power Platform environment

## Set up an Azure Health Data Services workspace

To work with Azure FHIR services, you need to set up a workspace and provision FHIR services.

> [!NOTE]
> If you already have access to an Azure Health Data Services setup, you can skip the following steps.

1.  Provision the workspace and related services. For instructions, see [Get started with Azure Health Data Services](/azure/healthcare-apis/get-started-with-health-data-services/?azure-portal=true).

1.  After the workspace is set up, you need to create the FHIR services. The following articles provide instructions on how to set up the FHIR service:

     -  [Get started with FHIR service](/azure/healthcare-apis/fhir/get-started-with-fhir/?azure-portal=true) 
 
     -  [Deploy a FHIR service within Azure Health Data Services - using portal](/azure/healthcare-apis/fhir/fhir-portal-quickstart/?azure-portal=true)

## Set up access to Azure Health Data Services

After you set up the services in your Azure subscription, you'll need to grant access to these services from other applications. The following steps and documentation help you set up access.

> [!NOTE]
> If you already have access to an Azure Health Data Services that's set up for application access, you can skip these steps. Make sure that you get a copy of the **Application/Client Id** and **Client Secret** for the existing app registration that has been granted access to your FHIR service.

### Set up application registration

Accessing Azure Health Data Services from external applications requires an app registration in Microsoft Entra as follows:

1. [Register a client application in Microsoft Entra ID](/azure/healthcare-apis/register-application/?azure-portal=true). This article provides background and steps for creating the app registration. Make sure that you copy the **Application/Client Id** and **Client Secret** that you create during these steps.

2. After you create the app registration, you need to grant access to the FHIR service by using Azure role-based access control (RBAC).

3. [Assign roles for the FHIR service](/azure/healthcare-apis/configure-azure-rbac?azure-portal=true#assign-roles-for-the-fhir-service). This article provides the steps for assigning the appropriate roles for your FHIR service by using role-based access control (RBAC). During this step, make sure that you assign the role named **FHIR Data Contributor**.

## Validate connectivity by using Postman

After you set up the services, you need to validate connectivity by using the **Postman** tool. For more information, see [Postman](https://www.getpostman.com/?azure-portal=true). You'll use this tool in later exercises to test and validate the new model-driven app.

### Set up a Postman workspace

Your next task is to set up a Postman workspace and then test connectivity to your **FHIR service**. For detailed steps, see [Access using Postman](/azure/healthcare-apis/fhir/use-postman/?azure-portal=true).

After you set up and validate connectivity, save the workspace for later exercises in this module.

## Set up Dataverse Healthcare APIs

After you set up Azure Health Data Services and validate connectivity, you can set up Dataverse Healthcare APIs so that you can post data to FHIR services and Dataverse. In this and later exercises, you use the logic app template that's available from Microsoft Cloud Solution Center as the entry point for FHIR bundles.

> [!NOTE]
> If you've already set up Dataverse Healthcare APIs and the relay logic app, you can skip the following steps.

### Dataverse healthcare APIs - Use the Healthcare data pipeline template to deploy Azure Logic Apps

Deploy a logic app by using an Azure Resource Manager template from **Microsoft Cloud Solution Center**. For detailed steps, see [Dataverse healthcare APIs: Configure Azure Logic App with an HTTP trigger](/dynamics365/industry/healthcare/dataverse-healthcare-apis-logic-app-deploy). Use details from your testing Dataverse environment and FHIR services during the Azure Resource Manager template deployment. In the article, follow the instructions that are outlined in the **Set up using a Healthcare data pipeline template** section.

## Set up virtual health data tables

After you complete the prerequisites, your system is set up to receive inbound FHIR data through Dataverse Healthcare APIs. Specifically, patient records are required because the parent link data for virtual health data tables are set up in the new model-driven app.

To connect virtual health data tables to the FHIR service, provide the connectivity information that you created when setting up the app registration in Microsoft Entra: the **Application/Client ID** and **Client Secret** values.

### Update the virtual health data tables integration settings

Use the detailed steps in the [Update FHIR server client ID and client secret](/dynamics365/industry/healthcare/virtual-health-data-tables-configure?azure-portal=true#update-fhir-server-client-id-and-client-secret) documentation to set up the Integration Settings feature for virtual health data tables in the Data integration toolkit.

Now, your system is ready to connect to the remote FHIR service in Dataverse by using virtual health data tables.
