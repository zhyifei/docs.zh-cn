---
title: 在开发过程中安全地存储应用程序机密
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 在开发过程中安全地存储应用程序机密
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: d8dd2da07104d6461d4eec0cb3fccd61c4db71c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580109"
---
# <a name="storing-application-secrets-safely-during-development"></a>在开发过程中安全地存储应用程序机密

若要连接受保护的资源和其他服务，ASP.NET Core 应用程序通常需要使用包含敏感信息的连接字符串、密码或其他凭据。 这些敏感的信息片段被称为“机密”。 最好不要在源代码中包含机密，当然也不要在源代码管理中存储机密。 相反，应使用 ASP.NET Core 配置模型从更安全的位置读取机密。

应将用于访问开发和暂存资源的机密与用于访问生产资源的机密分开，因为不同的个人需要访问不同的机密集。 若要存储在开发过程中使用的机密，常用的方法是在环境变量中或通过使用 ASP.NET Core 机密管理器工具存储机密。 为了在生产环境中实现更安全的存储，微服务可以将机密存储在 Azure Key Vault 中。

## <a name="storing-secrets-in-environment-variables"></a>在环境变量中存储机密

在源代码外部保存机密的一种方法是，开发者将基于字符串的机密设置为开发计算机上的[环境变量](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables)。 当使用环境变量来存储具有层次结构名称（嵌套在配置节中的名称）的机密时，为环境变量（包含机密名称的完整层次结构）创建一个名称，并用冒号 (:) 分隔。

例如，将环境变量 Logging:LogLevel:Default 设置为 Debug 将等效于以下 JSON 文件中的配置值：

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

若要从环境变量访问这些值，应用程序只需在构造 IConfigurationRoot 对象时调用其 ConfigurationBuilder 上的 AddEnvironmentVariables。

请注意，环境变量通常以纯文本形式存储，因此，如果计算机或带有环境变量的进程受到破坏，环境变量值将可见。

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>使用 ASP.NET Core 机密管理器存储机密

ASP.NET Core [机密管理器](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager)工具提供了在源代码外部保存机密的另一种方法。 若要使用“机密管理器”工具，请在项目文件中包含 Microsoft.Extensions.SecretManager.Tools 包的工具参考 (DotNetCliToolReference)。 一旦出现并恢复了该依赖关系，就可以使用 dotnet 用户机密命令来设置命令行中的机密值。 这些机密将存储在用户配置文件目录中的 JSON 文件中（详细信息随操作系统而异），与源代码无关。

机密管理器工具设置的机密是由使用机密的项目的 UserSecretsId 属性组织的。 因此，必须确保在项目文件（如下面的代码片段所示）中设置 UserSecretsId 属性。 用作 ID 的实际字符串并不重要，只要它在项目中是唯一的。

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

通过调用 ConfigurationBuilder 实例上的 AddUserSecrets&lt;T&gt; 将应用程序的机密包含在其配置中，就可以在应用程序中使用通过机密管理器存储的机密。 泛型参数 T 应是 UserSecretId 应用到的程序集中的类型。 通常可以使用 AddUserSecrets&lt;Startup&gt;。


>[!div class="step-by-step"]
[上一篇] (authorization-net-microservices-web-applications.md) [下一篇] (azure-key-vault-protects-secrets.md)
