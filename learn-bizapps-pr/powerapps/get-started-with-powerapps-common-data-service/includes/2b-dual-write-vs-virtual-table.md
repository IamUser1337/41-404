Microsoft Dataverse allows for many different connections to external data sources. Dual-write and virtual entities allow Dataverse to access this data and write back to the original data source. The purpose of this unit is to help you understand a bit about these exciting capabilities.

## Dual-write

Dual-write is an out-of-box infrastructure that provides near-real-time interaction between customer engagement apps and finance and operations apps. When data about customers, products, people, and operations flows beyond application boundaries, all departments in an organization are empowered.

Dual-write provides tightly coupled, bidirectional integration between finance and operations apps and Dataverse. Any data change in finance and operations apps causes writes to Dataverse, and any data change in Dataverse causes writes to finance and operations apps. This automated data flow provides an integrated user experience across the apps.

Dual-write also supports online and offline mode, and it follows the no-code/low-code principle.

Find more information about [Dual-write](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page/?azure-portal=true).

## Virtual entities

Finance and operations apps are a virtual data source in Dataverse, and enable full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform. By definition, the data for virtual entities doesn't reside in Dataverse. Instead, it continues to reside in the app where it belongs. Before CRUD operations can be performed on finance and operations entities from Dataverse, the entities must be made available as virtual entities in Dataverse. CRUD operations can then be performed from Dataverse and Microsoft Power Platform on data that resides in finance and operations apps.

All Open Data Protocol (OData) entities in finance and operations apps are available as virtual entities in Dataverse, and therefore also in Microsoft Power Platform. Makers can now use data directly from finance and operations apps to build experiences in customer engagement apps. These experiences offer full CRUD capability and don't require copying to Dataverse. Power Apps portals can be used to build external-facing websites that enable collaboration scenarios for business processes in finance and operations apps.

Find more information on [virtual entities](/dynamics365/fin-ops-core/dev-itpro/power-platform/virtual-entities-overview/?azure-portal=true).

## When to use Dual-write vs. virtual entities?

Together, virtual entities and dual-write are part of the shared data layer for the convergence of finance and operations apps and the Dataverse platform. They're complementary technologies that are intended to work together.

Dual-write is your best option when your data resides completely *inside* Dataverse, whether that's across environments in the same tenant, or between Dataverse and finance and operations apps. It provides near-real-time interaction between Dataverse and your Finance and Operations applications. Use it when you need your data to be available and up-to-date in your integrated environments.

Virtual entities seamlessly represent *external* data inside of Dataverse without replicating the data. Since virtual entities may be tapping into external data, it isn't replicated within Dataverse so it saves storage space. You can configure your virtual entities to display the latest information available, but it doesn't reside in Dataverse. If your data is for read-only, this may be a more appropriate approach for you, but it depends on the specific requirements of your project.
