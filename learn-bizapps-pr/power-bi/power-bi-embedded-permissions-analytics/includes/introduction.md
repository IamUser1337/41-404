When you're embedding Microsoft Power BI content, your app can restrict app user access to specific data. This is commonly achieved by datasets that enforce row-level security (RLS), which applies filters to model tables.

Consider an app at the Tailspin Toys company that embeds Power BI reports supporting its sales-effort analysis. Company policy compels the dataset developers to ensure that salespeople can view only the customer data for their assigned sales region. However, sales managers are permitted to view customer data for all sales regions. The dataset developer can create two RLS roles that apply different filters; one for salespeople and one for managers.

Also consider a *multitenancy* app. Multiple organizations use a multitenancy app, where each organization is a tenant. One approach to ensure that a tenant can view only their data is to use a single *multicustomer* database. This approach requires a single workspace that comprises one set of Power BI artifacts that are shared across all tenants. RLS will filter dataset data more securely to ensure that organizations can view only their data.

> [!NOTE]
> To learn more about multitenancy solutions, including a comparison of a separate database for each customer to a multicustomer database, see [Service principal profiles in Power BI Embedded](/power-bi/developer/embedded/embed-multi-tenancy/?azure-portal=true).

To gain a better understanding of how RLS restricts access to data, watch the following video.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VgMk]
