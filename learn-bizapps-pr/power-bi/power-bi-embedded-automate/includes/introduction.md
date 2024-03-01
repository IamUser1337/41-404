Developing an automation solution is useful when you need to reproduce management operations. Automation results in faster and more accurate solution management.

When you're developing apps that embed Power BI content, many opportunities are available for you to automate, including lifecycle management, adding new tenants (customers) in a multi-tenancy app, and various IT operations.

Here are three automation libraries that you can use:

- Microsoft Graph

- Microsoft Power BI REST API

- Power BI Embedded Azure Resource Manager (ARM) REST API

## Microsoft Graph

[Microsoft Graph](/graph/overview/?azure-portal=true) provides a unified programmability model. It exposes REST APIs and a client library to access data and perform operations on various Microsoft cloud services. Of relevance to automating Power BI solutions, Microsoft Graph can set up Microsoft Azure Active Directory security objects. Your app or PowerShell scripts can invoke Graph API calls.

The following script shows how to install the Azure AD PowerShell module for Graph in PowerShell. For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

```powershell
Install-Module -Name AzureAD
```

The following code blocks contribute to the first part of a PowerShell setup script to set up security objects for a new app that embeds Power BI content. Specifically, the code blocks show how to complete the following actions (in order):

1. Generate an Azure AD app secret

1. Create an Azure AD app registration

1. Create the Azure AD app registration's service principal

1. Assign the current user as the Azure AD app registration owner

1. Add the service principal to the **Power BI Apps** security group

The first code block initializes two variables. The `$appDisplayName` variable stores the new Azure AD app name, and the `$adSecurityGroupName` variable stores the name of an existing security group. In the Power BI tenant settings, a Power BI admin has already assigned this security group when allowing the use of service principals.

```powershell
# The new app display name
$appDisplayName = "My app"

# The name of an existing security group
$adSecurityGroupName = "Power BI Apps"
```

The next code block connects with an authenticated account to use Azure AD cmdlet requests. It also initializes variables with useful facts about the tenant and current user account. These facts are used by subsequent code blocks.

```powershell
$authResult = Connect-AzureAD

$tenantId = $authResult.TenantId.ToString()
$tenantDomain = $authResult.TenantDomain

$userAccountId = $authResult.Account.Id
$user = Get-AzureADUser -ObjectId $userAccountId
```

The next code block generates an app secret that becomes the password for an Azure AD app registration. The app secret is based on a GUID, and it's valid for one year from the current date.

```powershell
# Generate an app secret
$newGuid = New-Guid
$appSecret = ([System.Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes(($newGuid))))+"="
$startDate = Get-Date
$passwordCredential = New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordCredential
$passwordCredential.StartDate = $startDate
$passwordCredential.EndDate = $startDate.AddYears(1)
$passwordCredential.KeyId = $newGuid
$passwordCredential.Value = $appSecret
```

The next code block creates an Azure AD app registration by using the app secret.

```powershell
# Create an Azure AD app
$replyUrl = "https://localhost:5001/signin-oidc"

$aadApplication = New-AzureADApplication `
    -DisplayName $appDisplayName `
    -PublicClient $false `
    -AvailableToOtherTenants $false `
    -ReplyUrls @($replyUrl) `
    -Homepage $replyUrl `
    -PasswordCredentials $passwordCredential
```

The next code block creates the app registration's service principal. It also assigns the current user as the owner and adds the service principal to the security group.

```powershell
# Create the app's service principal
$appId = $aadApplication.AppId
$appObjectId = $aadApplication.ObjectId
$serviceServicePrincipal = New-AzureADServicePrincipal -AppId $appId
$serviceServicePrincipalObjectId = $serviceServicePrincipal.ObjectId

# Assign the current user as the app owner
Add-AzureADApplicationOwner -ObjectId $aadApplication.ObjectId -RefObjectId $user.ObjectId

# Add the service principal to the security group
Add-AzureADGroupMember -ObjectId $($adSecurityGroup.ObjectId) `
    -RefObjectId $($serviceServicePrincipalObjectId)
```

The following script variables contain useful information for your app. Their values should be written and added to the app's .config file.

- `$tenantDomain` - Required to authenticate with Azure AD.

- `$tenantId` - Required to authenticate with Azure AD.

- `$appId` - Required to generate an Azure AD access token.

- `$appSecret` - Required to generate an Azure AD access token. However, secrets shouldn't be deployed with the app. Instead, they should be accessed through a controlled means like environment variables or Microsoft Azure Key Vault. For more information, see [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets/?azure-portal=true).

The `$serviceServicePrincipalObjectId` variable stores a reference to the new service principal. In the next topic, a continuation of the script will use this variable.

## Power BI REST API

The [Power BI REST API](/rest/api/power-bi/?azure-portal=true) provides service endpoints for embedding, administration, governance, and user resources. Of relevance to automating Power BI solutions, the Power BI REST API can complete the following tasks:

- Create workspaces

- Assign a workspace to a capacity

- Set up workspace access

- Create and set up Power BI content

The following script shows how to install the Power BI management module in PowerShell. For more information, see [Microsoft Power BI cmdlets for Windows PowerShell and PowerShell Core](/powershell/power-bi/overview).

```powershell
Install-Module -Name MicrosoftPowerBIMgmt
```

The following code blocks contribute to the second part of a PowerShell setup script. It's a continuation of the script we described in the previous topic. The code blocks set up the Power BI environment. Specifically, they show how to complete the following tasks:

- Create a workspace.

- Add a service principal as the workspace admin.

- Import a Power BI Desktop file to create a dataset and report.

The first code block initializes two variables. The `$workspaceName` variable stores the new workspace name, and the `$pbixFilePath` variable stores the file path to a Power BI Desktop file.

```powershell
# The new workspace name
$workspaceName = "Sales Reporting"

# The file path to a Power BI Desktop file (.pbix)
$pbixFilePath = "D:\Sales Analysis.pbix"
```

The next code block connects to the Power BI service with an authenticated account. Then, attempts to retrieve a reference to the workspace. If the attempt fails (because the workspace doesn't exist), it creates the workspace. Lastly, the `$workspaceId` variable stores the workspace ID (called the GroupID).

```powershell
Connect-PowerBIServiceAccount

# Create the workspace (if it doesn't already exist)
$workspace = Get-PowerBIWorkspace -Name $workspaceName

if (!$workspace) {
    $workspace = New-PowerBIWorkspace -Name $workspaceName
}

$workspaceId = $workspace.Id
```

The next code block adds the service principal as a workspace admin.

```powershell
# Add the service principal as a workspace admin
Add-PowerBIWorkspaceUser -Scope Organization `
    -Id $workspaceId `
    -AccessRight Admin `
    -Identifier $serviceServicePrincipalObjectId `
    -PrincipalType App
```

The next code block imports a Power BI Desktop file into the new workspace.

```powershell
# Import the Power BI Desktop file
$import = New-PowerBIReport -Path $pbixFilePath -Workspace $workspace -ConflictAction CreateOrOverwrite
```

The `$workspaceId` variable contains useful information for your app. You should write the variable value and add it to the app's .config file. You can use the variable to enumerate workspace artifacts to retrieve properties that are required to embed them.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4VozC]

## Power BI Embedded ARM REST API

The Power BI Embedded ARM REST API allows you to create, retrieve, update, and delete Power BI Embedded capacities.

> [!NOTE]
> You can't use this API to manage Power BI Premium capacities. For more information, see [Configure and manage capacities in Power BI Premium](/power-bi/enterprise/service-admin-premium-manage/?azure-portal=true).

You can use the [Update](/rest/api/power-bi-embedded/capacities/update/?azure-portal=true) operation to scale a capacity resource; for example, when a sudden increase in demand occurs for computational resources. Other operations suspend or resume a capacity.

> [!NOTE]
> To learn about managing capacity resources and scale, see the [Select a Power BI embedded analytics](/training/modules/power-bi-embedded-select/) product module.

For more information, see [Power BI Embedded Azure Resource Manager REST API reference](/rest/api/power-bi-embedded/?azure-portal=true).
