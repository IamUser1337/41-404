Liquid extensions in Power Pages give makers access to Microsoft Dataverse. Table permissions govern all data that's accessed by Liquid objects and tags, and it's not possible to switch off this feature. Table permissions also make the output dynamic because it varies with the current website user, their web roles, and associated table permission rows.

To improve rendering performance and alter the template in response to the current user's privileges, developers can check particular access rights before implementing data retrieval. For example, instead of trying to access contact records, developers would check whether the user has Read privileges for the contact table and would then handle the response appropriately without retrieving the data.

Consider the following Liquid fragment:

```twig
{% if user %} <!-- 1 -->
<p>
  {% assign account = entities.account[user.parentcustomerid.id] %} <!-- 2 -->
  {% if account and account.permissions.can_read %} <!-- 3 -->
    Company: {{account.name}} <!-- 4 -->
  {% else %}
    Unknown company <!-- 5 -->
  {% endif%}
</p>
{% else %}
<p>We are unable to provide any information to anonymous visitors.</p> <!-- 6 -->
{% endif %}
```

In this example, the code completes the following actions:

1. Displays data only if the user is signed in.

1. Retrieves the parent account record.

1. Checks that the account exists and that the user has permissions to read that record. The **Permissions** property of the **table** object returns the  [Table Permissions](/power-pages/configure/liquid/liquid-objects?azure-portal=true#table-permissions) object that you can use to verify specific privileges.

1. Displays the name of the account, if available.

   Otherwise, it displays the "Unknown company" message.

1. Displays a generic message for anonymous visitors.

You can test the code inside Power Pages design studio and then go to the site. Check the different values that are rendered by the code because of the maker privileges within the design studio.

For more information, see [Liquid overview](/power-pages/configure/liquid/liquid-overview?azure-portal=true).
