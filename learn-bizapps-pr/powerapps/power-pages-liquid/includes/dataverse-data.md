Power Pages makers can use HTML to build the output that includes static content. Similarly, makers can use Liquid when working with multiple pages and dynamic content that comes from Microsoft Dataverse and when making changes from one page to the next. The Liquid elements act as placeholders, and before the output is sent to the browser, the Liquid elements are replaced by data from Dataverse.

Power Pages implements many extensions that are designed to work with Dataverse. Some [available Dataverse-specific Liquid objects](/power-pages/configure/liquid/liquid-objects?azure-portal=true) are described in the following table.

| Object        | Description                                                  |
| ------------- | ------------------------------------------------------------ |
| `page`        | Refers to the current website request page. The `page` object provides access to components such as the breadcrumbs for the current page, the title or URL of the current page, such as `{{ page.title }}`, and any other columns or related tables of the underlying Power Apps row. |
| `user`        | Refers to the current website user, allowing access to all columns of the underlying Power Apps contact row. If no user is signed in, this variable is `null`. |
| `website`     | Refers to the website, allowing access to all columns of the Power Apps Website (adx_website) row. |
| Generic&nbsp;tables | A table object provides access to the rows and columns in a Dataverse table. A collection of all tables is referred to as `entities`. For example, `{{ entities.contact[request.params.contactid].firstname }}` refers to the first name column in the contact row, identified by the `contactid` request parameter. |

You can use [Microsoft Dataverse-specific tags](/power-pages/configure/liquid/dataverse-liquid-tags?azure-portal=true) to load and display Dataverse data or to use other Power Pages framework services. These tags are Dataverse-specific extensions to the Liquid language. The following table describes some of these tags.

| Tag     | Description                                                  |
| ------- | ------------------------------------------------------------ |
| `chart` | Adds a Power Apps chart to a webpage. For steps to add a Power Apps chart to a webpage, see [Add a chart to a webpage in portal](/power-pages/configure/add-chart?azure-portal=true). |
| `powerbi`    | Adds the Microsoft Power BI dashboards and reports within pages. For steps to add a Power BI report or dashboard to a webpage on the website, see [Add a Power BI report or dashboard to a webpage](/power-apps/maker/portals/admin/add-powerbi-report?azure-portal=true). |
| `entitylist` | A Liquid block tag that loads a given list by name or ID. If the list loads successfully, the content within the block is rendered. |
| `entityview` | A Liquid block tag that loads a given Dataverse view by name or ID. If the view loads successfully, the content within the block is rendered. |
| `fetchxml`   | Allows users to query data from Dataverse and renders the results in a page. |
| `codecomponent` | Allows you to embed code components by using a Liquid tag. For more information, see [Use Liquid template tag for code components](/power-pages/configure/liquid/component-framework-liquid?azure-portal=true). |

In the following example, the **Active Currencies** view is being loaded and all returned rows are displayed. In Power Pages design studio, this code produces output because of the implicit design-time privileges of the maker. However, on the website, the user needs to have Read privileges assigned on the **currency** table for the fragment to return any data.

```php
{% entityview logical_name:'transactioncurrency', name:'Active Currencies' %}
<p>We support {{ entityview.total_records }} currencies.</p>
<ul>
  {% for cur in entityview.records -%}
  <li>{{ cur.currencyname }}</li>
  {% endfor %}
</ul>
{% endentityview %}
```

The output would resemble the following example:

> We support 4 currencies.
>
> * Australian dollar
> * Canadian dollar
> * Euro
> * US dollar

By using Liquid in Power Pages, you can:

- Add dynamic content directly to webpage content or to a content snippet.

- [Store source content by using web templates](/power-pages/configure/web-templates?azure-portal=true), entirely through configuration within Power Apps, for use throughout the Power Pages content management system.

- [Render a website header and primary navigation bar](/power-pages/configure/liquid/render-site-header-primary-navigation?azure-portal=true), entirely through configuration within Power Apps.

- [Use code components in Power Pages](/power-pages/configure/component-framework?azure-portal=true) that are built with  [Power Apps component framework](/power-apps/developer/component-framework/overview/?azure-portal=true) to provide an enhanced experience for users who are working with data on forms, views, and dashboards.

In these scenarios, you have dynamic access to Power Pages features, such as site settings, content snippets, lists and basic forms, and so on.

> [!IMPORTANT]
> Liquid statements are only processed as *output*. Liquid doesn't have the capacity to extend server-side code that deals with user interactions, such as form submissions.
