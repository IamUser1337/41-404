Microsoft Cloud for Healthcare provides a range of services and tools that help healthcare organizations manage their data and improve patient care.

## Azure Health Data Services

**Azure Health Data Services** helps organizations share electronic health records (EHR) and electronic medical records (EMR) on a range of devices in a more secure and compliant manner. Azure Health Data Services boosts the exchange of data through FHIR APIs, backed by a managed platform as a service (PaaS) offering in the cloud. These new APIs support more standards than the Microsoft Azure API for FHIR, including Digital Imaging and Communications in Medicine (DICOM) and Internet of Things (IoT). As a result, healthcare organizations can integrate their data from different systems and devices, helping to improve interoperability between different systems.

## Data integration toolkit

The **Data integration Toolkit** helps simplify data admin duties by providing ready-made entity maps that associate Fast Healthcare Interoperability Resources (FHIR) with Microsoft Dataverse entities, attribute maps that associate FHIR resource elements with Dataverse attributes, and logs that capture details on the Dataverse Healthcare API activities. The Data integration toolkit helps healthcare organizations sync patients' protected health information (PHI) data between EHR systems and Dataverse. It includes ready-to-use and customizable entity maps, attribute maps, and management tools, which help healthcare admins control data that flows between FHIR servers and Microsoft Dataverse. As a result, healthcare organizations can integrate their data from different systems and ensure that patient data is up to date and accurate across all devices.

## Virtual health data tables

**Virtual health data tables** optimize your cloud hosting spend by virtualizing your clinical reference data and other healthcare data when you're using model-driven apps and other engagement solutions. This feature removes the need for you to build expensive integrations that visualize the same data-intensive tables multiple times across Microsoft and other applications, such as electronic health record (EHR) systems. By virtualizing their data, healthcare organizations can share patient data between different systems and devices in a more secure and compliant manner.

## Healthcare data pipeline template

Microsoft Cloud for Healthcare also provides healthcare database templates in Microsoft Azure Synapse. These templates act as blueprints that provide common elements that are derived from best practices, government regulations, and the complex data and analytic needs of an industry-specific organization. You can use these information blueprints to plan and design data solutions for data governance, reporting, business intelligence, and advanced analytics.

These tools and services are a few of many that are available in Microsoft Cloud for Healthcare to help organizations manage their healthcare data. Together, these components provide a comprehensive solution for healthcare organizations that want to improve their integration and interoperability.

Follow these steps to create a data integration solution to transfer only patient FHIR resource data from an external EHR system to Microsoft Dataverse by using the Data integration toolkit, virtual health data tables, Azure Health Data Services, and Healthcare data pipeline template:

1. **Set up patient records to flow into Dataverse by using the Data integration toolkit** - The Data integration toolkit simplifies data admin duties by providing ready-made entity maps that associate FHIR resources with Dataverse entities, attribute maps that associate FHIR resource elements with Dataverse attributes, and logs that capture details on the Dataverse Healthcare API activities.

1. **Deploy Microsoft Azure Logic Apps by using the Data Ingestion ARM Template** - This step helps you set up a template logic app that serves as a relay for inbound FHIR bundles to ensure posting to Dataverse and the FHIR server.

1. **Set up the managed identity in Data integration toolkit** - This step helps you set up the virtual data source attributes (FHIR Server URL, Auth, and Resource).

1. **Switch the targeted data routes to virtual** - This step helps you use the virtual health data tables in Microsoft Cloud for Healthcare to virtualize your clinical reference data and other healthcare data when you're using model-driven apps and other engagement solutions.

1. **Use Azure Health Data Services** - Azure Health Data Services boosts the exchange of data through FHIR APIs, backed by a managed platform as a service (PaaS) offering in the cloud. These new APIs support more standards than the Azure API for FHIR, including DICOM and IoT.
