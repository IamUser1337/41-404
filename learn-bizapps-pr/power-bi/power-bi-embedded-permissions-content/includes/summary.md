Setting up permissions is an important part of your app development. It involves selecting the appropriate authentication flow for the embedding scenario. When you're using the *For your customers* scenario, you must also decide whether to use a service principal or master user account embedding identity. We recommend service principal for production apps. It's more secure, though it requires a Power BI tenant admin to set up and manage.

To embed Power BI content, your app must first acquire an access token. When you use the *For your organization* scenario, access tokens are Azure AD tokens. When you use the *For your customers* scenario, access tokens are embed tokens, which your app generates by using the Power BI REST API.

> [!TIP]
> If you're interested in developing an app that embeds Power BI content, see [Power BI Developer in a Day course](https://aka.ms/deviad-online-course/?azure-portal=true). This course includes a self-study kit that guides you through developing an ASP.NET Core MVC app. The app uses the *For your customers* scenario and the embedding identity is a security principal.
