Non-standardized data creates critical problems. Coordinated care, patient monitoring, alerts, and flexible care options are among the many healthcare functions that rely on interoperability.

Azure Health Data Services helps address some of the most common challenges to interoperability, including:

- **Health data is siloed.** Care and innovation are stifled without an ability to cross-reference or merge coincident data from different sources.
- **Health data structures are non-uniform.** Translating non-uniform health data into a standard format can be labor-intensive and error-prone. This challenge is a material barrier to AI/machine learning and analytics workloads.
- **De-identification of non-uniform data is difficult and time-consuming.** De-identification of data is often required by law.
- **Geographically unique** datasets are difficult to transform for research (that is, population health data).
   
## Solve interoperability challenges

Azure Health Data Services is an Azure PaaS service that enables organizations to bring health data to the Microsoft cloud. Health Data Services enables health organizations to ingest, convert, and de-identify protected health information (PHI) to enable health data interoperability within and across organizations.

Health Data Services focuses on several internationally adopted data standards, including FHIR® and DICOM®. Health Level Seven International (HL7®) publishes a standard for healthcare data exchange, [FHIR®](https://www.hl7.org/fhir/index.html). It enables a robust, extensible data model with standardized semantics and data exchange that allows all systems that use FHIR® to work together. By transforming data to FHIR®, users can quickly connect together existing data sources, such as electronic health record systems or research databases. SMART on FHIR, which is an extension of the base FHIR® standard, enables the rapid exchange of data in modern implementations of mobile and web development. By using the SMART on FHIR standard, app developers can better apply harmonized health datasets and exchange those datasets between systems. Additionally, FHIR® can simplify data ingestion and accelerate development with analytics and machine learning tools.

FHIR® provides an alternative to document-centric approaches by directly exposing discrete data elements as resources. For example, basic elements within health records, such as patients, admissions, diagnostic reports, and medications, can be retrieved and manipulated through their own resource URLs. 

A FHIR resource is a discrete data concept, such as a patient, document, medication, family history, health procedure, and a list of allergies.

:::image type="content" source="../media/fhir-data-sources.png" alt-text="Picture of a patient, document, medication, family history, health procedure, and list of allergies pushed to the cloud. These examples are sources of FHIR® content." lightbox="../media/fhir-data-sources.png":::

Currently, HL7 designates 145 types of resources. A FHIR® resource is a piece of data that you can collect across the internet. It has a physical location that you can locate through a URL address submitted in a browser. This feature, combined with canonized terms and extensions of those terms, makes FHIR® a key aspect of improving interoperability.

While FHIR®, as a standard, enables interoperability for better patient outcomes, it's not a replacement IT system for payors, providers, or for research or pharmaceutical organizations. FHIR® doesn't replace electronic health record (EHR) systems or provider billing systems. FHIR® enables the data to be exchanged by these systems, by calling the FHIR service.

Azure Health Data Services and FHIR® enable data interoperability in the following key areas:

- **Health data in a centralized repository** - Health Data Services enables organizations to store and organize their data in a centralized location.
- **Creating data uniformity** - Normalized data is universally readable across the health and life sciences sector.
- **Providing more secure, de-identified data** - Health organizations can apply this data for research, clinical, and operational insights.
- **Health Data Services is the *babelfish*** - In the cloud, Health Data Services translates data structures into globally recognized formats.

:::image type="content" source="../media/api-azure-data-service.png" alt-text="Diagram shows two wheels and how data is used in Azure Health Data Services." lightbox="../media/api-azure-data-service.png"::: 

## Healthcare data connectors
After the health data is processed, you can use it in reporting and analytics for Microsoft Power BI data visualizations, Microsoft Teams notifications, SMART on FHIR user-facing apps, and more. Additionally, you can use the de-identified data to train models in Microsoft Azure Machine Learning for identifying patterns and outliers to aid practitioners in making decisions.  

## PHI ready
Protected health information (PHI) is regulated with protections that allow for a more secure transfer of information that is needed to provide care. This information is personal and includes data such as vitals, diagnosis, care plans, and so on. 
