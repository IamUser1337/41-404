Microsoft Cloud for Healthcare provides a range of services and tools that help healthcare organizations manage their data and improve patient care. One service is **Azure Health Data Services**, which organizations use to share electronic health records (EHR) and electronic medical records (EMR) on a range of devices in a more secure and compliant manner. Azure Health Data Services boosts the exchange of data through FHIR APIs, backed by a managed platform as a service (PaaS) offering in the cloud. These new APIs support more standards than the Azure API for FHIR, including Digital Imaging and Communications in Medicine (DICOM) and Internet of Things (IoT). As a result, healthcare organizations can integrate their data from different systems and devices, which improves interoperability between different systems.

Another tool that's available in Microsoft Cloud for Healthcare is the **Data integration toolkit**. This toolkit simplifies data admin duties by providing the following features:

- Entity maps that associate FHIR resources with Dataverse entities

- Attribute maps that associate FHIR resource elements with Dataverse attributes

- Logs that capture details on the Dataverse Healthcare API activities. 
 
The Data integration toolkit helps healthcare organizations sync patients' protected health information (PHI) data between EHR systems and Dataverse. It includes ready-to-use and customizable entity maps, attribute maps, and management tools, which help healthcare admins control data that's flowing between FHIR servers and Microsoft Dataverse. As a result, healthcare organizations can integrate their data from different systems and ensure that patient data is up to date and accurate across all devices.

Virtual health data tables in Microsoft Cloud for Healthcare optimize your cloud hosting spend by virtualizing your clinical reference data and other healthcare data when you're using model-driven apps and other engagement solutions. This solution removes the need for you to build expensive integrations that visualize the same data-intensive tables multiple times across Microsoft and other applications, such as electronic health record (EHR) systems. By virtualizing their data, healthcare organizations can share patient data between different systems and devices in a more secure and compliant manner.

With virtual health data tables, Microsoft, customers, partners, and ISVs can build FHIR-focused applications within Dataverse that directly access the FHIR services. You can use the virtualized tables in solutions as you would normally use standard Dataverse tables when you're building model-driven apps. Support for create, update, and delete operations helps users update the virtualized data directly on the FHIR service, bypassing the need for complex syncing. After you sync the required data in Dataverse, such as patient records, the related virtual records can remain in the FHIR services.

These tools and services are some of many that are available in Microsoft Cloud for Healthcare that help organizations manage their healthcare data. Together, these components provide a comprehensive solution for healthcare organizations that want to improve their integration and interoperability.

You can create a data integration solution to transfer only **patient** FHIR resource data from an external EHR system to Microsoft Dataverse by using the Data integration toolkit, virtual health data tables, Azure Health Data Services, and Healthcare data pipeline template. To do so, follow these steps:

1. **Set up patient data to flow into Dataverse by using the Data integration toolkit** - The Data integration toolkit simplifies data admin duties by providing ready-made entity maps that associate FHIR resources with Dataverse entities, attribute maps that associate FHIR resource elements with Dataverse attributes, and logs that capture details on the Dataverse Healthcare API activities.

2. **Deploy Azure Logic Apps by using the Data Ingestion ARM Template** - This step helps you set up a template Logic Apps application that serves as a relay for inbound FHIR bundles to ensure the posting to Dataverse and the FHIR server.

3. **Set up the managed identity in Data integration toolkit** - This step helps you set up the virtual data source attributes (FHIR Server URL, Auth, and Resource).

4. **Switch the targeted data routes to virtual** - This step helps you use virtual health data tables in Microsoft Cloud for Healthcare to virtualize your clinical reference data and other healthcare data when you're using model-driven apps and other engagement solutions.

5. **Use Azure Health Data Services** - Azure Health Data Services boosts the exchange of data through FHIR APIs, backed by a managed platform as a service (PaaS) offering in the cloud. These new APIs support more standards than the Azure API for FHIR, including DICOM and IoT.

By following these steps, you can create a data integration solution to sync patient FHIR data from an external EHR system, such as Azure Health Data Services, to Microsoft Dataverse by using the Data integration toolkit while linking to external FHIR data by using virtual health data tables.
