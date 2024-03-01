Multiple organizations can use a *multi-tenancy app*, where each organization is a tenant. A multi-tenancy app that embeds Power BI analytics will use the *For your customers* scenario because the app users include external users. When designing a multi-tenancy app, you can choose from two different tenancy models.

The recommended approach is to use the *workspace separation* model. You can achieve this approach by creating one Power BI workspace for each tenant. Each workspace contains Power BI artifacts that are specific to that tenant, and the datasets connect to a separate database for each tenant.

Alternatively, the single *multi-customer database* model is available. When you use this model, your solution will achieve separation with a single workspace that includes a set of Power BI artifacts that are shared across all tenants. Row-level security (RLS) roles, which are defined in the datasets, will help filter the data more securely to ensure that organizations only view their own data.

> [!NOTE]
> To learn more about enforcing RLS, see the [Enforce data permissions for Power BI embedded analytics](/training/modules/power-bi-embedded-permissions-analytics/) module.
>
> To learn more about multi-tenancy solutions, including a comparison of a separate database for each customer to a multi-customer database, see [Service principal profiles in Power BI Embedded](/power-bi/developer/embedded/embed-multi-tenancy/?azure-portal=true).

When you're using the workspace separation model, start by creating a *golden workspace*. A golden workspace is a template workspace that contains default Power BI artifacts, including datasets, reports, and dashboards. Whenever a new tenant is introduced, an automation solution will replicate the golden workspace content to a new workspace.

The automation solution can use the following steps to add a new tenant:

1. Use Microsoft Graph to create a service principal.

1. Use the Power BI REST API to add the service principal as a contributor to the golden workspace.

1. By using the new service principal, the automation solution will use the Power BI REST API to:

    1. Create a workspace for the new tenant.

    1. Replicate the golden workspace content to the new workspace.

    1. Update the dataset connections to connect to the tenant data.

    1. Assign the new workspace to a capacity.

> [!NOTE]
> Creating a new service principal for each tenant isn't necessary. However, we recommend that you create a service principal profile for each tenant workspace to achieve the highest possible isolation. For more information, see [Service principal profiles in Power BI Embedded](/power-bi/developer/embedded/embed-multi-tenancy/?azure-portal=true).

To gain a better understanding of how to automate workspace separation, watch the following video.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VozD]
