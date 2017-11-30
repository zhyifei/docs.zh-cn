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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>使用 Azure 密钥保管库在生产时保护机密

机密存储为环境变量或存储机密管理器工具仍是存储在本地和在计算机上以未加密状态。 用于存储机密更加安全的选项是[Azure 密钥保管库](https://azure.microsoft.com/services/key-vault/)，它提供用于存储密钥和机密一个安全的中央位置。

Microsoft.Extensions.Configuration.AzureKeyVault 包允许 ASP.NET Core 应用程序从 Azure 密钥保管库中读取配置信息。 若要开始使用 Azure 密钥保管库中的机密，请按照下列步骤：

首先，将你的应用程序注册为 Azure AD 应用程序。 （Azure AD 管理是对密钥保管库的访问）。可以通过 Azure 管理门户完成此操作。

或者，如果你希望应用程序而不密码或客户端机密使用证书进行身份验证，则可以使用[New-azurermadapplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet。 向 Azure 密钥保管库注册的证书需要仅公匙。 （你的应用程序将使用私钥）。

其次，通过创建新的服务主体授予到密钥保管库的已注册应用程序访问。 你可以执行此操作使用以下 PowerShell 命令：

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

第三，通过调用 IConfigurationBuilder.AddAzureKeyVault 扩展方法时创建 IConfigurationRoot 实例包括作为你的应用程序中的配置源的密钥保管库。 请注意，调用 AddAzureKeyVault 将需要在已注册并授予对前面的步骤中的密钥保管库访问权限的应用程序 ID。

  目前，标准.NET 和.NET 核心支持获取配置信息从 Azure 密钥保管库使用客户端 ID 和客户端密钥。 .NET framework 应用程序可以使用采用代替客户端密钥的证书的 IConfigurationBuilder.AddAzureKeyVault 的重载。 截至撰写本文时，工作是[正在](https://github.com/aspnet/Configuration/issues/605)标准.NET 和.NET 核心中提供该重载。 直到接受证书不可用的 AddAzureKeyVault 重载，ASP.NET Core 应用程序可以访问 Azure 密钥保管库使用基于证书的身份验证通过显式创建的 KeyVaultClient 对象，如下面的示例中所示：

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

在此示例中，调用 AddAzureKeyVault 附带的配置提供程序注册末尾。 它是一种最佳做法以将 Azure 密钥保管库注册为最后一个配置提供程序，和，使其具有的重写从以前的提供程序的配置值的机会，使来自其他源没有配置值重写那些从密钥保管库。

## <a name="additional-resources"></a>其他资源

-   **使用 Azure 密钥保管库来保护应用程序机密**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **安全存储在开发过程中的应用程序机密**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **配置数据保护**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **密钥管理以及生存期**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#数据保护的默认设置*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets。** GitHub 存储库。
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[以前](开发人员的应用程序的机密-storage.md) [下一步] (.../ 密钥 takeaways.md）
