SharePoint includes a Representational State Transfer (REST) service that is comparable to the existing SharePoint client object models. Now, developers can interact remotely with SharePoint data by using any technology that supports REST web requests. Essentially, developers can perform create, read, update, and delete (CRUD) operations from their SharePoint add-ins, solutions, and client applications by using REST web technologies and standard Open Data Protocol (OData) syntax.

## How the SharePoint REST service works

SharePoint adds the ability for you to remotely interact with SharePoint sites by using REST. Now, you can interact directly with SharePoint objects by using any technology that supports standard REST capabilities.

To access SharePoint resources by using REST, you can construct a RESTful HTTP request by using the OData standard, which corresponds to the desired client object model API, as shown in the following example:

```odata
GET https://{site_url}/_api/lists/getbytitle('{list_name}')/items
Authorization: "Bearer " + accessToken
Accept: "application/json;odata=verbose"
```

## Use HTTP commands with SharePoint REST service

To use the REST capabilities that are built into SharePoint, you can construct a RESTful HTTP request by using the OData standard, which corresponds to the client object model API that you want to use. The client.svc web service handles the HTTP request and serves the appropriate response in either Atom or JSON format. Then, the client application must parse that response.

The endpoints in the SharePoint REST service correspond to the types and members in the SharePoint client object models. By using HTTP requests, you can use these REST endpoints to do typical CRUD operations against SharePoint entities, such as lists and sites.

The following table provides an overview of the HTTP requests.

|     Action    |     HTTP request    |     Keep in mind                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------|--------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Read a   resource                          |     GET                        |     The returned   data format might need to be modified.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|     Create or   update a resource              |     POST                       |     Use POST to   create entities such as lists and sites.     The   SharePoint REST service supports sending POST commands that include object   definitions to endpoints that represent collections.     For POST   operations, properties that aren't required are set to their default   values.     If you   attempt to set a read-only property as part of a POST operation, the service   returns an exception.                                                                                                                                                        |
|     Update or   insert a resource              |     PUT                        |     Use PUT and MERGE   operations to update existing SharePoint objects.     Any service   endpoint that represents an object property set operation supports PUT   requests and MERGE requests.     For MERGE   requests, setting properties is optional; properties that you don't   explicitly set keep their current property.     For PUT   requests, if you don't specify all required properties in object updates, the   REST service returns an exception.     Optional   properties that you don't explicitly specify are set to their default properties.    |
|     Delete a   resource                        |     DELETE                     |     Use the HTTP   DELETE command against the specific endpoint URL to delete the SharePoint   object that is represented by that endpoint.     Recyclable objects are available, such as lists, files, and list items, which results in a   Recycle operation.                                                                                                                                                                                                                                                                                                                                |

## Construct REST URLs to access SharePoint resources

SharePoint uses REST APIs. An API is a software intermediary that allows two applications to talk to each other. Each time that you use an app on your phone to check the weather, you are using an API.

To construct SharePoint REST service endpoints, follow these steps:

1. Start with the REST service reference:

    `https://{site_url}/_api`

2. Specify the appropriate entry point, for example:

    `https://{site_url}/_api/web`

    Example: `https://contoso.sharepoint.com/_api/web`

3. Go from the entry point to the specific resources that you want to access, including specifying parameters for endpoints that correspond to methods in the client object model, for example:

    `https://{site_url}/_api/web/lists/getbytitle('list_name')`

    Example: `https://contoso.sharepoint.com/_api/Lists/getbytitle('TestList')`
