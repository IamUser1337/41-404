All types of Power BI content are embedded client-side by using a `div` element. You use the Power BI client API to embed Power BI content. It involves passing in a configuration object that provides all the information required to embed Power BI content. Some of that information must be obtained server-side by using the Power BI REST API, which you can use to retrieve artifact IDs and embed URLs.

Consider optimizing the embedding experience by using bootstrap, which prepares and initializes the `iframe` element before all required configuration parameters are set, or phased embedding, which can speed up embedding when the embedded content is on a different page of your app.

> [!TIP]
> If you're interested in developing an app that embeds Power BI content, see [Power BI Developer in a Day course](https://aka.ms/deviad-online-course/?azure-portal=true). This course includes a self-study kit that guides you through developing an ASP.NET Core MVC app. The app dynamically generates menu options allowing app users to select which Power BI content to embed. The app embeds Power BI reports and the Q&A experience.
