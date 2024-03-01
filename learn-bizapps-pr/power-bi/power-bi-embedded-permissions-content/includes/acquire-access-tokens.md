When you acquire an access token, which your app always requires to embed Power BI content, involves acquiring an Azure AD token. When you use the *For your customers* scenario, the app uses the Azure AD token to generate an embed token.

To be clear:

- The access token for the *For your organization* scenario is the **Azure AD token**, which contains claims that your app uses to identify granted permissions.
- The access token for the *For your customers* scenario is an **embed token**, which represents facts about Power BI content and how your app can access them. Your app generates the embed token by using a Power BI REST API operation, which requires an Azure AD token.

## Acquire Azure AD tokens

Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview/?azure-portal=true) to develop app logic that acquires Azure AD tokens from the Microsoft identity platform. MSAL supports different application architectures and platforms including .NET, JavaScript, Java, Python, Android, and iOS.

> [!TIP]
> When developing an ASP.NET Core web app, we recommend that you use the [Microsoft Identity Web authentication library](/azure/active-directory/develop/microsoft-identity-web/?azure-portal=true). This library is a set of packages known as **Microsoft.Identity.Web**. You can install it from NuGet or Visual Studio.

There are different techniques to acquire an Azure AD token by using MSAL. Some require user interaction through a web browser, while others don't require any user interaction. In general, the method you choose to acquire an Azure AD token depends on whether the application is a public client application (like a desktop or mobile app) or a confidential client application (like a web app). The embedding scenario also impacts on your choice.

It's not this unit's intention to describe the techniques that acquire Azure AD tokens. For more information, see [Acquire and cache tokens using the Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-acquire-cache-tokens/?azure-portal=true).

> [!TIP]
> When the Embedding setup tool sample apps match your app requirements, consider copying the sample code to acquire Azure AD tokens.

To allow your app to acquire Azure AD tokens, its config file should contain the following settings:

- `TenantId` - Required for service principal only. It's your Azure AD TenantID.
- `ClientId` - Required. It's your Azure AD app ApplicationID (ClientID).
- `ClientSecret` or `ClientCertificate` - Required for service principal only.
- `PbiUsername` - Required for master user account only.
- `PbiPassword` - Required for master user account only.

> [!IMPORTANT]
> Whether using certificates, client secrets, or master user account credentials, you must take steps to protect them from unauthorized access and use. We recommend using [Azure Key Vault](/azure/key-vault/general/security-features/?azure-portal=true), which protects cryptographic keys, certificates, and secrets in the cloud.

## Acquire embed tokens

Use the `GenerateTokenRequestV2` operation of the [Microsoft Power BI REST API](/azure/active-directory/develop/msal-overview/?azure-portal=true) to request an embed token. There are other related operations that generate embed tokens for other Power BI content types. All API operations require an Azure AD token.

> [!TIP]
> When developing a .NET app, we recommend that you install the [Microsoft.PowerBI.Api](https://www.nuget.org/packages/Microsoft.PowerBI.Api/?azure-portal=true) package. You can install it from NuGet or Visual Studio.

Consider the following code that shows how to generate an embed token. The token contains claims for all reports and datasets from a workspace, and allows app users to create or edit reports. Specifically, it does the following:

1. Connects to Power BI.
1. Declares a variable named `reportTokenRequests` to store report-token requests.
1. Enumerates all reports in the workspace, creating a list of `EmbeddedReport` objects (using a helper class). Each object describes the report's ID, name, and embed URL. The app requires the report ID to generate a token. The name is required to present to users in a menu, and the embed URL is required to embed the report. The code adds a report token request, allowing report editing, to the `reportTokenRequests` variable.
1. Declares a variable named `datasetTokenRequests` to store dataset token requests.
1. Enumerates all datasets in the workspace, creating a list of `EmbeddedDataset` objects (using a helper class). Each object describes the dataset's ID, name, and embed URL. The app requires the dataset's ID to generate a token. The name may be required to present it to users in a menu, and the embed URL is required to embed the dataset. The code adds a dataset token request to the `datasetTokenRequests` variable.
1. Generates a workspace token request (required when users create reports) that's added to the `workspaceRequests` variable.
1. Uses the `GenerateTokenRequestV2` method to bundle together the report token requests, dataset token requests, and the workspace token request.
1. Uses `GenerateTokenAsync` to generate an embed token.
1. Stores the embed token in a string variable.

```csharp
// Connect to Power BI
var client = GetPowerBiClient();

// Get reports in the workspace
var reports = (await client.Reports.GetReportsInGroupAsync(_workspaceId)).Value;

var reportList = new List<EmbeddedReport>();
var reportTokenRequests = new List<GenerateTokenRequestV2Report>();

foreach (var report in reports)
{
    reportList.Add(new EmbeddedReport
    {
        Id = report.Id.ToString(),
        Name = report.Name,
        EmbedUrl = report.EmbedUrl
    });

    reportTokenRequests.Add(new GenerateTokenRequestV2Report(report.Id, allowEdit: true));
}

// Get datasets in the workspace
var datasets = (await client.Datasets.GetDatasetsInGroupAsync(_workspaceId)).Value;

var datasetList = new List<EmbeddedDataset>();
var datasetTokenRequests = new List<GenerateTokenRequestV2Dataset>();

foreach (var dataset in datasets)
{
    datasetList.Add(new EmbeddedDataset
    {
        Id = dataset.Id.ToString(),
        Name = dataset.Name,
        EmbedUrl = dataset.QnaEmbedURL
    });

    datasetTokenRequests.Add(new GenerateTokenRequestV2Dataset(dataset.Id));
}

// Generate token request for the workspace
var workspaceRequests = new GenerateTokenRequestV2TargetWorkspace[] {
    new GenerateTokenRequestV2TargetWorkspace(_workspaceId)
};

// Bundle token requests for reports, datasets, and the workspace
var tokenRequest = new GenerateTokenRequestV2(
    reports: reportTokenRequests,
    datasets: datasetTokenRequests,
    targetWorkspaces: workspaceRequests
);

// Generate the embed token
string embedToken = (await client.EmbedToken.GenerateTokenAsync(tokenRequest)).Token;
```

The app should output the `embedToken` variable value to the embedding HTML page. Client-side logic can then use the embed token to embed content in a `div` element.

> [!NOTE]
> To learn how to embed Power BI content, work through the [Embed Power BI content](/training/modules/power-bi-embedded-content/?azure-portal=true) module.

To allow your app to acquire embed tokens, its config file should contain details about the embeddable content. It can include specific ReportIDs and DatasetIDs, or more commonly the GroupIDs of the workspaces that contain embeddable content.

For more information, see [Embed Token - Generate Token](/rest/api/power-bi/embed-token/generate-token/?azure-portal=true).

## Refresh access tokens

Access tokens have an expiration time. Once they're generated, app users have limited time to interact with Power BI content that uses them. In order to provide your app users with a continuous experience, your app should refresh access tokens before they expire by using the Power BI client API.

> [!NOTE]
> To learn about the Client API, work through the [Integrate content with the Power BI client APIs](/training/modules/power-bi-embedded-integrate/?azure-portal=true) module.

For more information, see [Refresh the access token](/javascript/api/overview/powerbi/refresh-token/?azure-portal=true).

## Explore other resources

To learn more, watch the [Power BI Developers Guide to Azure AD Security](https://www.youtube.com/watch?v=NoWCBfo0zU4&list=PL2RaY7gpgPCEaJvxdB7C23Ws5711KmFaW) video series. This series consists of six videos that cover in-depth theory. Ted Pattison, who is a member of the Power BI Customer Advisory Team (CAT) at Microsoft, produced this video series.
