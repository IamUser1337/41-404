The platform doesn't provide an infinite amount of resources, and limits are imposed on the number of API calls that can be made.

A solution architect needs to ensure that the solution doesn't exceed the limits that are imposed by the platform by designing appropriately and ensuring that custom code can handle when limits are breached.

## API requests

Requests in Microsoft Power Platform consist of various actions that a user makes across various products. The following list describes what constitutes an API request, at a high level:

- **Power Apps** - All API requests to connectors and Microsoft Dataverse.
- **Power Automate** - All API requests to connectors, HTTP actions, and built-in actions from initializing variables to a simple compose action. Both succeeded and failed actions count toward these limits. Additionally, retries and other requests from pagination count as action implementations. As a basic rule, each step in a Power Automate cloud flow is an API request.
- **Dataverse** - All create, read, update, and delete (CRUD), assign, and share operations, including user-driven and internal system requests that are required to complete CRUD transactions, as well as special operations like share or assign. These requests can be from any client or application and can use any endpoint. These requests include, but aren't limited to, plug-ins, classic workflows, and custom controls that are making the previously mentioned operations.

## Entitlement limits

Entitlement limits represent the number of API requests that users are entitled to make each day. The allocated limit depends on the type of license that is assigned to each user. API entitlement limits are based on a 24-hour period, as shown in the following table.

| Products | Requests per paid license per 24 hours |
|--------------|-------------------|
|Paid licensed users for Power Platform (excludes Power Apps per App, Power Automate per flow, and Power Virtual Agents) and Dynamics 365 excluding Dynamics 365 Team Member|40,000|
|[Power Apps pay-as-you-go plan](https://go.microsoft.com/fwlink/?linkid=2173947), and paid licensed users for Power Apps per app, Microsoft 365 apps with Power Platform access, and Dynamics 365 Team Member|6,000|
|Power Automate per flow plan, Power Virtual Agents base offer, and Power Virtual Agents add-on pack| 250,000|
|Paid Power Apps Portals sign in |200|

Dataverse provides the ability to have identities that don't require a user license to interact with the service. The four types of users are:

- Application users
- Non-interactive users
- Administrative users
- SYSTEM user

Each tenant has a base request capacity for each tenant that can only be used by these users and not by users with standard licenses. This base request capacity is based on the type of subscription, as follows:

- If a tenant has at least one Dynamics 365 enterprise subscription, they get 100,000 requests every 24 hours.
- If a tenant has at least one Dynamics 365 professional subscription, they get 50,000 requests every 24 hours.
- If a tenant has at least one Microsoft Power Apps or Power Automate subscription, they get 25,000 requests every 24 hours.

Power Apps and Power Automate capacity add-on allows customers to increase the limits for a given user. Each capacity add-on raises the request limits by another 10,000 every 24 hours.

> [!NOTE]
> For more information, see [API request limits](/power-platform/admin/api-request-limits-allocations/?azure-portal=true).

## Service limits

Apart from the daily API request limit, service protection limits are available that are specific to each service. As with the daily limits, service limits help maintain the quality of service by protecting the service from malicious or noisy behavior that would otherwise disrupt service for all customers.

Service protection API limits help ensure that users who are running applications can't interfere with each other based on resource constraints. The limits won't affect normal users of the platform. Only applications that perform numerous API requests might be affected. The limits provide a level of protection from random and unexpected surges in request volumes that threaten the availability and performance characteristics of the Dataverse platform.

Microsoft limits the number of concurrent connections for each user account, the number of API requests for each connection, and the amount of run time that can be used for each connection. These limitations are evaluated within a five-minute sliding window. When one of these limits is exceeded, an exception will be thrown by the platform.

> [!IMPORTANT]
> Service protection limits can't be increased.

> [!NOTE]
> For more information, see [API limits](/power-apps/maker/data-platform/api-limits-overview/?azure-portal=true).

## Retry policies and patterns

Custom logic that uses the APIs should handle retries. When a service protection API limit error occurs, it provides a value indicating that the duration before any new requests from the user can be processed.

The Web API returns a 429 error if the limit is reached. The response includes a **Retry-After** with the number of seconds. With the Organization Service, a TimeSpan value is returned in the OrganizationServiceFault.ErrorDetails collection with the key **Retry-After**.

> [!NOTE]
> Care should be taken to ensure that you don't make it worse by over retrying.

For more information, see [Service protection limits](/power-apps/developer/data-platform/api-limits/?azure-portal=true).

## Minimize API calls

The solution design must not depend on infinite capacity being available. For normal users of interactive apps, the limits have been set high enough that users shouldn't be affected.

Applications that are designed to load data into Dataverse or perform bulk updates must also be able to manage service protection API limit errors. These applications prioritize throughput so that they can complete their work in the minimum amount of time. These applications must have a strategy to retry operations.

Portal applications typically send requests from anonymous users through a service principal account. Because the service protection API limits are based on a user-by-user basis, portal applications can reach service protection API limits based on the amount of traffic that the portal experiences.

Integrations should be optimized to minimize the number of API calls.

The solution architect must also consider high availability in the design of the solution.
