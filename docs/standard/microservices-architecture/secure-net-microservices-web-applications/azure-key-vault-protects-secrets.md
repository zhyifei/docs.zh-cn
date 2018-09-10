---
title: 在生产时使用 Azure Key Vault 保护机密
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在生产时使用 Azure Key Vault 保护机密
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5738b81c90c886aff48451742881807dc09a9ff9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464890"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>在生产时使用 Azure Key Vault 保护机密

存储为环境变量的机密或由机密管理器工具存储的机密仍在本地存储并在计算机上解密。 用于存储机密更加安全的选项是使用 [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)，它为存储密钥和机密提供安全的中央位置。

Microsoft.Extensions.Configuration.AzureKeyVault 包允许 ASP.NET Core 应用程序从 Azure Key Vault 中读取配置信息。 若要开始通过 Azure Key Vault 使用机密，请按照下列步骤操作：

首先，将你的应用程序注册为 Azure AD 应用程序。 （对密钥保管库的访问由 Azure AD 管理。）可以通过 Azure 管理门户完成此操作。

或者，如果希望应用程序使用凭据而非密码或客户端密码进行身份验证，则可以使用 [New-AzureRmADApplication](https://docs.microsoft.com/powershell/module/azurerm.resources/new-azurermadapplication) PowerShell cmdlet。 向 Azure Key Vault 注册的证书仅需要公钥。 （你的应用程序将使用私钥。）

其次，通过创建新的服务主体授予已注册应用程序访问密钥保管库权限。 可以使用以下 PowerShell 命令来执行此操作：

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

第三，创建 IConfigurationRoot 实例时通过调用 IConfigurationBuilder.AddAzureKeyVault 扩展方法将密钥保管库作为配置源包括在应用程序中。 请注意，调用 AddAzureKeyVault 将需要前面步骤中已注册并已获取密钥保管库访问权限的应用程序 ID。

  目前，.NET Standard 和 .NET Core 支持使用客户端 ID 和客户端密码从 Azure Key Vault 获取配置信息。 .NET framework 应用程序可以使用采用证书代替客户端密码的 IConfigurationBuilder.AddAzureKeyVault 的重载。 截至撰写本文时，我们[仍在](https://github.com/aspnet/Configuration/issues/605)努力使该重载在 .NET Standard 和 .NET Core 中可用。 直到接受证书的 AddAzureKeyVault 重载可用之前，ASP.NET Core 应用程序可以通过显式创建 KeyVaultClient 对象使用基于证书的身份验证来访问 Azure Key Vault，如下面的示例中所示：

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

在此示例中，在配置提供程序注册的最后调用 AddAzureKeyVault。 最好将 Azure Key Vault 注册为最后一个配置提供程序，使其有机会重写具有之前提供程序的配置值，这样就没有其他源的配置值重写密钥保管库中的值。

## <a name="additional-resources"></a>其他资源

-   **使用 Azure Key Vault 保护应用程序密码**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **在开发期间安全存储应用密码**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **配置数据保护**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **密钥管理和生存期**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   Microsoft.Extensions.Configuration.KeyPerFile GitHub 存储库。
    [*https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile*](https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile)

>[!div class="step-by-step"]
[上一页](developer-app-secrets-storage.md)
[下一页](../key-takeaways.md)
