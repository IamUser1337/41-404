Azure Health Data Services consists of tools and connectors for protected health information to enable health and life sciences systems interoperability within and across organizations. The following diagram shows a high-level example of its key components.

:::image type="content" source="../media/tools-connectors.png" alt-text="Diagram of a database, IoT device, medical image, and biomedical image, showing their connection to the Azure workspace." lightbox="../media/tools-connectors.png":::

## Azure Health Data Services workspace

The Azure Health Data Services workspace is a logical container for healthcare service instances, such as the Fast Healthcare Interoperability Resources (FHIR®) services, the Digital Imaging and Communications in Medicine (DICOM®) services, and the MedTech service.

Key workspace concepts: 

- The workspace creates a compliance boundary (HIPAA, HITRUST) within which protected health information can travel.
- You can provision multiple services within a workspace so that they work more seamlessly with one another.
- You can create workspaces in a resource group from the Azure portal or by using deployment scripts.
- Workspaces provide a single compliance boundary for authentication and authorization of users.
- Role-based access control (RBAC) enables you to manage how your data is stored and accessed.
- Data is isolated to a unique database for each API instance and is more protected with multi-region failover.

The following diagram illustrates how Azure Health Data Services might be provisioned in an Azure subscription.

:::image type="content" source="../media/azure-resource-group.png" alt-text="Diagram of a group of the resources, namely the DICOM®, the MedTech service, the FHIR® service, and the standard configuration settings." lightbox="../media/azure-resource-group.png":::

## The FHIR® service
The FHIR® service in Azure Health Data Services enables rapid exchange of data through FHIR APIs, which are backed by a managed platform-as-a service (PaaS) offering in the cloud, with the ability to use all resources on the Microsoft stack. 

Key FHIR® service concepts:

- The FHIR API and compliant data store enable you to more securely connect and interact with any system that uses FHIR APIs.
- By transforming your data to FHIR, you can connect existing data sources, such as the electronic health record systems or research databases.
- Enables to ingress and egress the data into the FHIR® service with high throughput. 
- The FHIR® service allows for the exchange of data through consistent, RESTful, FHIR APIs based on the HL7 FHIR® specification.

:::image type="content" source="../media/azure-fhir-rest-api.png" alt-text="Diagram of the Post, Get, Put, Patch, and Delete syntax for the RESTful API." lightbox="../media/azure-fhir-rest-api.png":::

## The DICOM® service
DICOM® (Digital Imaging and Communications in Medicine) is the international standard to transmit, store, retrieve, print, process, and display medical imaging information. It's the primary medical imaging standard that's accepted across healthcare. For example, DICOM® helps enable digitization of ultrasound, CT scan, MRI, and other common imaging procedures.

The following diagram illustrates how DICOM® is used to transfer DICOM objects between entities, such as hospitals, payors, and other medical centers for second opinions or continued care.  
 
:::image type="content" source="../media/dicom-objects.png" alt-text="Diagram of a hospital, insurance company, medical center, and how they interact." lightbox="../media/dicom-objects.png":::

The DICOM data model consists of four object levels: Patient, Study, Series & Equipment, and Instance (image).

:::image type="content" source="../media/dicom-data-model.png" alt-text="Diagram shows the four object levels of Patient, Study, Series & Equipment, and Instance." lightbox="../media/dicom-data-model.png":::

The DICOM® service is a managed service within Azure Health Data Services that ingests and persists DICOM® objects at multiple thousands of images per second.

Key DICOM® service concepts:

- Facilitate communication and transmission of imaging data with any DICOMweb™ enabled systems or applications through DICOMweb™ standard APIs.
- Isolate data to a unique database for each API instance and help protect with multi-region failover.
- Index DICOM studies, series, and instances on standard and private DICOM® tags by expanding the list of tags that are already specified within the DICOM® Conformance Statement.
- Access ordered, guaranteed, immutable, read-only logs of all changes that occur in the DICOM® service.
- Inject DICOM metadata into the FHIR® service, or the FHIR® server, as an imaging study resource. This feature allows for a single source of truth for clinical data and imaging metadata.

## MedTech service
You can use the MedTech service to ingest, and transform to FHIR®, high-frequency data from IoT digital health devices. You can use this data for monitoring, storage, analysis, and reporting of vital health information.

:::image type="content" source="../media/medtech-service.png" alt-text="Diagram of a hospital, ambulance, lab, and a house, showing information collection from them and the information being sent to the MedTech service." lightbox="../media/medtech-service.png":::

With MedTech service, you can:
- Align and standardize health data from disparate devices into a common format to make sense of the data through a unified lens and to capture trends.
- Normalize and group IoT data by mapping commonalities to FHIR®.
- Link devices and health care consumers for enhanced insights and trend capture.
- Use MedTech service with devices that are created and managed through Azure IoT Hub for enhanced workflows and ease of use.

## Deploy Azure Health Data Services
You can set up Azure Health Data Services by using the Azure portal or programmatically by using Bicep.  

:::image type="content" source="../media/azure-services-deploy.png" alt-text="Screenshot of the UI page for creating a resource, with the Overview tab open." lightbox="../media/azure-services-deploy.png":::

As part of creating the Azure Health Data Services resource, you can provide details to stand up a workspace.

:::image type="content" source="../media/create-workspace.png" alt-text="Screenshot of the UI page for creating a workspace, with the Basic tab open." lightbox="../media/create-workspace.png":::

On the **Basic** tab, select your Azure **Subscription**, the **Resource group** where you want to deploy the Health Data Services workspace, and the **Region** where you're located. Also, you need to supply a name for your workspace.

After you created the workspace, you can deploy the individual services. Each service has its own configuration that you would need to complete. 

With Azure Health Data Services, you pay only for what you use with consumption-based pricing. Auto scale ensures that the service meets the varying demands of your workload.
