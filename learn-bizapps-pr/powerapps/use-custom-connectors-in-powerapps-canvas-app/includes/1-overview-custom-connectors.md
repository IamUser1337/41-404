If you built your first canvas app in Power Apps, you may be
thinking how you can extend your app by calling a publicly available
API, or a custom API you're hosting in a cloud provider, such as Azure.
To support such tailored scenarios, you can build custom connectors with
triggers and actions. Because these connectors are function-based, they
will call specific functions in the underlying service of the API to
return the corresponding data.

An advantage of building custom connectors is that they can be used in
different platforms, such as
[Power Apps](https://powerapps.microsoft.com/), [Power Automate](https://flow.microsoft.com/), and [Azure Logic
Apps](https://azure.microsoft.com/services/logic-apps).

Creating custom connectors
----------------------------------------

You can create custom connectors using three different approaches:

- [Using a blank custom connector](/connectors/custom-connectors/define-blank/?azure-portal=true)

- [From an OpenAPI definition](/connectors/custom-connectors/define-openapi-definition/?azure-portal=true)

- [From a Postman collection](/connectors/custom-connectors/define-postman-collection/?azure-portal=true)

While the requirements for each approach will vary, they all require either a per user/app/month or a per user/month for all users using the app. Each link
above points to the instructions for each approach. You'll learn how to
create a custom connector from a Postman collection in a later unit.
