In this unit, you set up a virtual health data table to access observation data from Azure FHIR server by completing the following tasks:

- Register a Microsoft Entra app to set up a virtual health data table.

- Grant the Microsoft Entra app with the FHIR Data Contributor role on Azure FHIR Server.

- Set up a virtual health data table.

- Update data routes of the Observation table and its supporting tables to virtual.

## Register the Microsoft Entra app to set up a virtual health data table

In this task, you use the Azure portal to register an app in the Microsoft Entra ID that you used to set up the virtual health data table.

1. Follow the steps from [Microsoft Cloud for Healthcare training environment preparation](/training/modules/training-environment-preparation-healthcare/4a-azure-trial/?azure-portal=true) to register a Microsoft Entra app.

1. Set up the Microsoft Entra app by using the following details:

    - **Name** - VirtualHealthDataApp

    - **Supported account types** - Accounts in this organizational directory only

1. After registering the Microsoft Entra app, copy its **Client ID** and then save it on a notepad for later use in this unit.

1. Select **Certificates & secrets** on the left panel.

1. On the right panel, select **+ New client secret**.

1. Create a new client secret, copy its value, and then store it in a notepad for later use in this unit.

## Grant the Microsoft Entra app access to the Azure FHIR Server

In this task, you use the Azure portal to grant the Microsoft Entra app with the FHIR Data Contributor role on the Azure FHIR Server.

Follow the steps from [Microsoft Cloud for Healthcare training environment preparation](/training/modules/training-environment-preparation-healthcare/4a-azure-trial/?azure-portal=true) to register a Microsoft Entra app.

## Update data routes

In this task, you use the Data integration toolkit of Microsoft Cloud for Healthcare to update the data routes of the **Observation** table and its supporting tables to read the Observation data directly from the Azure FHIR server instead of Dataverse. For more information, see [Update data route to Dataverse or virtual](/dynamics365/industry/healthcare/virtual-health-data-tables-configure?#update-data-route-to-dataverse-or-virtual).
 

