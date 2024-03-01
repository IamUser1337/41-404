Fast Healthcare Interoperability Resources (FHIR®, pronounced "fire") is an industry standard that specifies a universal structure for health data. The main purpose of FHIR® is to ease data sharing between different organizations and health data systems. The FHIR® standard was created by Health Level Seven International (HL7), a global non-profit health data organization.

## FHIR® key tenets

The FHIR® key tenets are as follows:

- **An extensible data model for healthcare that serves to normalize health data.** For example, with FHIR, the canonical data model for a patient always follows the same structure so that patient data is transferable from one system to another.

- **An API specification for exchanging health data between systems.** The specification provides a framework for sending and receiving FHIR data over the internet by using a common data transfer protocol.

- **A set of profiles and implementation guides for putting the FHIR® standard into use in real-world healthcare operations.** FHIR® conformance guidelines are available on the [HL7 website](https://build.fhir.org/conformance-module.html?azure-portal=true).

- **A community of implementers that brings the standards to life.** The global health and life sciences community uses the FHIR data model and API to promote health data interoperability.

FHIR® normalizes the structure and exchange of health information, which allows payors, providers, researchers, and patients move health data electronically wherever the data is needed, across different healthcare scenarios, systems, and organizations.

Key points about the FHIR® standards are that they're:

- Mandated in the United States.

- Globally adopted.

- Founded in web standards.

- Human readable.

- Structured to enable straightforward adoption through shared profiles.

FHIR® is a next-generation standards framework that's designed to enable health data interoperability. FHIR® is built on previous data format standards, such as HL7v2, but FHIR® expands on these older standards by incorporating modern web-based technologies, including:

- An HTTP RESTful protocol.

- XHTML and CSS for user interface integration.

- A choice of JSON, XML, or RDF for data representation.

One goal with FHIR® is to facilitate interoperability between legacy health data systems so that organizations, providers, and patients can share health data across traditional obstacles and boundaries.

FHIR® differs from traditional document-based data storage by structuring healthcare data around the people, places, and other entities that are connected with real-world healthcare interactions. These people, places, and other entities are referred to as "resources" in FHIR. For example, in FHIR, healthcare data is structured as:

- A web of connections to a Patient resource (for a specific patient).

- A Practitioner resource (for a specific provider).

- An Encounter resource (to store information about a care visit).

- A DiagnosticReport resource.

FHIR resources offer extensive coverage of the entities that are connected with the healthcare process, including resources for devices, insurance plans, scheduling, survey questions, and other items that are related to healthcare. Resources in FHIR are also continually being added because FHIR® is an evolving standard.

Because FHIR® is implemented on top of HL7 and the HTTPS (HTTP Secure) protocol, messages can be parsed by applications that listen for "events" in FHIR® (that is, specific changes in FHIR data). In this frame, healthcare organizations are able to gather near real-time data from FHIR resources as they're created or updated. Then, the system will process data with custom business logic to trigger preset actions and workflows. Potential use cases include epidemic tracking, adverse drug interaction warnings, care team notifications, and more.

## FHIR® principles

FHIR® aligns to the following architectural principles:

- **Reuse and composability** - The FHIR data model is built with the 80/20 rule as its guiding principle. Prioritize the 20 percent of requirements that enable 80 percent of interoperability scenarios.

- **Scalability** - Transactions are stateless to reduce memory usage and support horizontal scalability.

- **Performance** - Suitable for rapid exchange across networks.

- **Usability** - FHIR resources are human-readable and viewable in text editors/browsers.

- **Data fidelity** - FHIR has strict data typing built in with support for clinical terminology coding systems and a mechanism for performing data validation against standard profiles. Ways to extend profile definitions with custom business logic for rules-based validation are available.

- **Implementable** - FHIR® is ready to implement by using industry standards and by developing SMART on FHIR® applications that can connect to a FHIR server from mobile and web-based applications.
