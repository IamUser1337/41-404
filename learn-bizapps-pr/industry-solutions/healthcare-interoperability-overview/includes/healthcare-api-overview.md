Dataverse Healthcare APIs are included as a full product offering from Microsoft Cloud for Healthcare. These APIs enable you to interact with Microsoft Dataverse by using the FHIR standard. The APIs use the Entity and Attribute maps in Data Integration Toolkit to transform the bundles between FHIR and Dataverse. Additionally, these APIs support writeback capabilities to FHIR Server in Azure and other FHIR servers.

As of now, the Dataverse Healthcare APIs set has the following endpoints:

-   **Upsert bundle API** - With this API, you can send FHIR bundles directly to Dataverse to transform them into Dataverse records. The upsert bundle API is named **msind_UpsertBundle**. The two request parameters are:

    -  **msind_JSON** - This parameter is required, and it accepts a JSON FHIR bundle that needs to be inserted in Dataverse.

    -  **msind_BundleTag** - This parameter is optional. When you use this parameter, it helps you identify the bundles while parsing the logs in Data Integration Toolkit.

    Capabilities supported by the upsert bundle API include:

    -  Supports ingestion of the **batch** and **batch-response** bundle types. The **Transaction** and other bundle types aren't supported. For more information, see [FHIR Resource Bundle](https://www.hl7.org/fhir/R4/bundle.html?azure-portal=true#using).

    -  Ingests a bundle that contains entries for a single FHIR resource type, such as Patient or Practitioner.

    -  Ingests a bundle that contains entries for mixed FHIR resource types, such as Patient, Practitioner, Medication, or Claims.

    -  Ingests a bundle with Uniform Resource Name (URN) reference.

    -  Ensures the referential integrity of FHIR bundles. Essentially, a resource is only be created in Dataverse if all its references are resolved.

    -  Creates expanded records for each FHIR resource in Dataverse.

    -  Creates codeable concepts when they're missing in Dataverse.

    -  Supports verbose and localized responses.

-   **Retrieve bundle API** - This API enables you to query Dataverse for a single FHIR resource (single record) by using the FHIR ID. The API uses the Entity and Attribute maps in Data Integration Toolkit to transform the request to respond with a FHIR standardized resource. It also supports verbose and localized logging. The retrieve bundle API is named **msind_RetrieveBundle** and has the request parameter of **msind_FHIRQuery**, which is a required parameter that takes the FHIR query to implement.

The retrieve bundle API supports passing the following two types of FHIR queries to its **msind_FHIRQuery** parameter.

|     Query                                                              |     Description                                                                                                                                                                             |
|------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     FHIRResource/FHIRID                                                |     The query returns the entire resource along with the expanded   entities.                                                                                                           |
|     FHIRResource/FHIRId?_elements=element_1,element_2,...,element_n    |     The query returns the elements that are specified in the query along with elements that are marked as FHIR Required on the Attribute map. For more   information, see [FHIR Element Search](https://www.hl7.org/fhir/search.html?azure-portal=true#elements).    |

> [!IMPORTANT]
> Don't create new patients in Dataverse. Always add new patients in your FHIR server and then let Data Integration Toolkit and the ingestion pipeline create the corresponding Dataverse records.
>
> Patients are the core resource (entity) in FHIR. Every other resource (entity) in FHIR relates to the Patient resource or entity. FHIR servers automatically assign a unique ID when you add a new patient. That ID attribute is read-only. If you try to create a new patient record in Dataverse, Dataverse can't assign a value to the patient ID (FHIR ID) attribute in FHIR. As a result, Data Integration Toolkit and the data ingestion pipeline can't write the data changes to your FHIR system.
>
> When you add a new patient in your EMR system, the data change will flow to the Azure FHIR server and then to Dataverse. Then, you can add related records, such as encounters, appointments, and observations.
