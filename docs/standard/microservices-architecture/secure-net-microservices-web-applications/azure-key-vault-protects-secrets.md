---
title: 在生产时使用 Azure Key Vault 保护机密
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在生产时使用 Azure Key Vault 保护机密
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5ad5686909c29eba5916cbcc4b7115a16108a004
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580398"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="d82cf-103">在生产时使用 Azure Key Vault 保护机密</span><span class="sxs-lookup"><span data-stu-id="d82cf-103">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="d82cf-104">存储为环境变量的机密或由机密管理器工具存储的机密仍在本地存储并在计算机上解密。</span><span class="sxs-lookup"><span data-stu-id="d82cf-104">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="d82cf-105">用于存储机密更加安全的选项是使用 [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)，它为存储密钥和机密提供安全的中央位置。</span><span class="sxs-lookup"><span data-stu-id="d82cf-105">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="d82cf-106">Microsoft.Extensions.Configuration.AzureKeyVault 包允许 ASP.NET Core 应用程序从 Azure Key Vault 中读取配置信息。</span><span class="sxs-lookup"><span data-stu-id="d82cf-106">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="d82cf-107">若要开始通过 Azure Key Vault 使用机密，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d82cf-107">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="d82cf-108">首先，将你的应用程序注册为 Azure AD 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d82cf-108">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="d82cf-109">（对密钥保管库的访问由 Azure AD 管理。）可以通过 Azure 管理门户完成此操作。</span><span class="sxs-lookup"><span data-stu-id="d82cf-109">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="d82cf-110">或者，如果希望应用程序使用凭据而非密码或客户端密码进行身份验证，则可以使用 [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d82cf-110">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="d82cf-111">向 Azure Key Vault 注册的证书仅需要公钥。</span><span class="sxs-lookup"><span data-stu-id="d82cf-111">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="d82cf-112">（你的应用程序将使用私钥。）</span><span class="sxs-lookup"><span data-stu-id="d82cf-112">(Your application will use the private key.)</span></span>

<span data-ttu-id="d82cf-113">其次，通过创建新的服务主体授予已注册应用程序访问密钥保管库权限。</span><span class="sxs-lookup"><span data-stu-id="d82cf-113">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="d82cf-114">可以使用以下 PowerShell 命令来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="d82cf-114">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="d82cf-115">第三，创建 IConfigurationRoot 实例时通过调用 IConfigurationBuilder.AddAzureKeyVault 扩展方法将密钥保管库作为配置源包括在应用程序中。</span><span class="sxs-lookup"><span data-stu-id="d82cf-115">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="d82cf-116">请注意，调用 AddAzureKeyVault 将需要前面步骤中已注册并已获取密钥保管库访问权限的应用程序 ID。</span><span class="sxs-lookup"><span data-stu-id="d82cf-116">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="d82cf-117">目前，.NET Standard 和 .NET Core 支持使用客户端 ID 和客户端密码从 Azure Key Vault 获取配置信息。</span><span class="sxs-lookup"><span data-stu-id="d82cf-117">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="d82cf-118">.NET framework 应用程序可以使用采用证书代替客户端密码的 IConfigurationBuilder.AddAzureKeyVault 的重载。</span><span class="sxs-lookup"><span data-stu-id="d82cf-118">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="d82cf-119">截至撰写本文时，我们[仍在](https://github.com/aspnet/Configuration/issues/605)努力使该重载在 .NET Standard 和 .NET Core 中可用。</span><span class="sxs-lookup"><span data-stu-id="d82cf-119">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="d82cf-120">直到接受证书的 AddAzureKeyVault 重载可用之前，ASP.NET Core 应用程序可以通过显式创建 KeyVaultClient 对象使用基于证书的身份验证来访问 Azure Key Vault，如下面的示例中所示：</span><span class="sxs-lookup"><span data-stu-id="d82cf-120">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="d82cf-121">在此示例中，在配置提供程序注册的最后调用 AddAzureKeyVault。</span><span class="sxs-lookup"><span data-stu-id="d82cf-121">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="d82cf-122">最好将 Azure Key Vault 注册为最后一个配置提供程序，使其有机会重写具有之前提供程序的配置值，这样就没有其他源的配置值重写密钥保管库中的值。</span><span class="sxs-lookup"><span data-stu-id="d82cf-122">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d82cf-123">其他资源</span><span class="sxs-lookup"><span data-stu-id="d82cf-123">Additional resources</span></span>

-   <span data-ttu-id="d82cf-124">**使用 Azure Key Vault 保护应用程序密码**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="d82cf-124">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="d82cf-125">**在开发期间安全存储应用密码**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="d82cf-125">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="d82cf-126">**配置数据保护**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="d82cf-126">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="d82cf-127">**密钥管理和生存期**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="d82cf-127">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="d82cf-128">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="d82cf-128">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="d82cf-129">GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="d82cf-129">GitHub repo.</span></span>
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="d82cf-130">[上一页] (developer-app-secrets-storage.md) [下一页] (../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="d82cf-130">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
