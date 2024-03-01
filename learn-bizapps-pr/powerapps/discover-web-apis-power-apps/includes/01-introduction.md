While developing a Power Apps app, you may find out you need to call a web API created by a high-code, or traditional, development team in your organization. The Power Apps ecosystem already has hundreds of *connectors* to access resources inside and outside your organization. However, there is not a built-in connector for you to call web APIs that your organization has developed. You have to create a *custom connector* to fill the gap between Power Apps and web APIs.

In a previous module on how Fusion Development practices help businesses create better applications faster, you met the team at VanArsdel, Ltd, and how they plan to use fusion development to fix issues they are experiencing with their Field Inventory Management System.

There are two members on VanArsdel's fusion development team so far, Kiana and Maria. Kiana is a professional developer who creates ASP.NET Core web APIs to use internally and externally. Maria is an inventory management specialist who creates applications with Power Apps to help her with her job responsibilities.

They are working together to create a new Power Apps app that helps manage inventory. Their first task is to display a list of VanArsdel's warehouse locations. The warehouse locations will be fetched from a web API and displayed in the Power Apps app.


## Learning objectives ##

In this module, you will:

* Learn what a custom connector is, and its use cases,
* Build a custom connector from a web API deployed in Visual Studio,
* Build a custom connector from a web API deployed in Azure API Management,
* Build a custom connector from an OpenAPI document, and
* Test and use a custom connector to call a web API from a Power Apps app.


## Prerequisites ##

* Familiarity with the concept of web (HTTP) APIs.
