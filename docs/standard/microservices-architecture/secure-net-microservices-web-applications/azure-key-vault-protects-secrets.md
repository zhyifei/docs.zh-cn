---
title: "使用 Azure 密钥保管库在生产时保护机密"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |使用 Azure 密钥保管库在生产时保护机密"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="b0921-104">使用 Azure 密钥保管库在生产时保护机密</span><span class="sxs-lookup"><span data-stu-id="b0921-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="b0921-105">机密存储为环境变量或存储机密管理器工具仍是存储在本地和在计算机上以未加密状态。</span><span class="sxs-lookup"><span data-stu-id="b0921-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="b0921-106">用于存储机密更加安全的选项是[Azure 密钥保管库](https://azure.microsoft.com/services/key-vault/)，它提供用于存储密钥和机密一个安全的中央位置。</span><span class="sxs-lookup"><span data-stu-id="b0921-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="b0921-107">Microsoft.Extensions.Configuration.AzureKeyVault 包允许 ASP.NET Core 应用程序从 Azure 密钥保管库中读取配置信息。</span><span class="sxs-lookup"><span data-stu-id="b0921-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="b0921-108">若要开始使用 Azure 密钥保管库中的机密，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="b0921-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="b0921-109">首先，将你的应用程序注册为 Azure AD 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b0921-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="b0921-110">（Azure AD 管理是对密钥保管库的访问）。可以通过 Azure 管理门户完成此操作。</span><span class="sxs-lookup"><span data-stu-id="b0921-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="b0921-111">或者，如果你希望应用程序而不密码或客户端机密使用证书进行身份验证，则可以使用[New-azurermadapplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b0921-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="b0921-112">向 Azure 密钥保管库注册的证书需要仅公匙。</span><span class="sxs-lookup"><span data-stu-id="b0921-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="b0921-113">（你的应用程序将使用私钥）。</span><span class="sxs-lookup"><span data-stu-id="b0921-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="b0921-114">其次，通过创建新的服务主体授予到密钥保管库的已注册应用程序访问。</span><span class="sxs-lookup"><span data-stu-id="b0921-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="b0921-115">你可以执行此操作使用以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="b0921-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="b0921-116">第三，通过调用 IConfigurationBuilder.AddAzureKeyVault 扩展方法时创建 IConfigurationRoot 实例包括作为你的应用程序中的配置源的密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="b0921-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="b0921-117">请注意，调用 AddAzureKeyVault 将需要在已注册并授予对前面的步骤中的密钥保管库访问权限的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="b0921-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="b0921-118">目前，标准.NET 和.NET 核心支持获取配置信息从 Azure 密钥保管库使用客户端 ID 和客户端密钥。</span><span class="sxs-lookup"><span data-stu-id="b0921-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="b0921-119">.NET framework 应用程序可以使用采用代替客户端密钥的证书的 IConfigurationBuilder.AddAzureKeyVault 的重载。</span><span class="sxs-lookup"><span data-stu-id="b0921-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="b0921-120">截至撰写本文时，工作是[正在](https://github.com/aspnet/Configuration/issues/605)标准.NET 和.NET 核心中提供该重载。</span><span class="sxs-lookup"><span data-stu-id="b0921-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="b0921-121">直到接受证书不可用的 AddAzureKeyVault 重载，ASP.NET Core 应用程序可以访问 Azure 密钥保管库使用基于证书的身份验证通过显式创建的 KeyVaultClient 对象，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="b0921-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

<span data-ttu-id="b0921-122">在此示例中，调用 AddAzureKeyVault 附带的配置提供程序注册末尾。</span><span class="sxs-lookup"><span data-stu-id="b0921-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="b0921-123">它是一种最佳做法以将 Azure 密钥保管库注册为最后一个配置提供程序，和，使其具有的重写从以前的提供程序的配置值的机会，使来自其他源没有配置值重写那些从密钥保管库。</span><span class="sxs-lookup"><span data-stu-id="b0921-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0921-124">其他资源</span><span class="sxs-lookup"><span data-stu-id="b0921-124">Additional resources</span></span>

-   <span data-ttu-id="b0921-125">**使用 Azure 密钥保管库来保护应用程序机密**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="b0921-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="b0921-126">**安全存储在开发过程中的应用程序机密**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="b0921-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="b0921-127">**配置数据保护**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="b0921-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="b0921-128">**密钥管理以及生存期**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#数据保护的默认设置*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="b0921-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="b0921-129">**Microsoft.Extensions.Configuration.DockerSecrets。**</span><span class="sxs-lookup"><span data-stu-id="b0921-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="b0921-130">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="b0921-130">GitHub repo.</span></span>
    [<span data-ttu-id="b0921-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="b0921-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="b0921-132">[以前](开发人员的应用程序的机密-storage.md) [下一步] (.../ 密钥 takeaways.md）</span><span class="sxs-lookup"><span data-stu-id="b0921-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
