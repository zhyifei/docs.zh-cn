---
title: "在开发过程中安全地存储应用程序机密"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |在开发过程中安全地存储应用程序机密"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a>在开发过程中安全地存储应用程序机密

若要连接与受保护的资源和其他服务，ASP.NET Core 应用程序通常需要使用连接字符串、 密码或包含敏感信息的其他凭据。 这些敏感的信息片段称为*机密*。 它是一种最佳做法不在源代码中包含机密而肯定不是存储在源代码管理中的机密。 相反，应使用 ASP.NET Core 配置模型从更安全的位置读取的机密。

你应将分开的机密访问开发和过渡与用于访问生产资源，因为不同的个人需要对这些不同的机密集的访问的资源。 若要存储在开发过程中使用的机密，常用的方法是在环境变量中或通过使用 ASP.NET 核心机密 Manager 工具或者存储机密信息。 有关在生产环境中的更安全存储，微服务可以在 Azure 密钥保管库存储机密。

## <a name="storing-secrets-in-environment-variables"></a>在环境变量中存储机密

保留源代码之外的机密的一种方法是为开发人员设置基于字符串的机密作为[环境变量](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables)在其开发计算机上。 当使用环境变量来存储具有层次结构名称 （那些嵌套在配置节中） 的机密，创建一个环境变量的名称，包含机密的名称的完整层次结构时，用冒号 （:） 分隔。

例如，将日志记录： LogLevel:Default 的环境变量设置为调试将等效于配置值从下面的 JSON 文件：

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

若要从环境变量访问这些值，应用程序只需在其 ConfigurationBuilder 上调用 AddEnvironmentVariables 构造 IConfigurationRoot 对象时。

请注意，环境变量通常存储为纯文本，因此，如果计算机或使用环境变量的进程受到攻击，环境变量值将会可见。

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>存储机密使用 ASP.NET 核心机密管理器

ASP.NET 核心[机密 Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager)工具提供了另一种方法来保留源代码之外的机密。 若要使用密码管理器工具，包括你的项目文件中的 Microsoft.Extensions.SecretManager.Tools 包工具参考 (DotNetCliToolReference)。 一旦该依赖关系存在并已还原，dotnet 用户机密命令可以用于从命令行设置机密的值。 这些机密将存储在用户的配置文件目录 （详细信息因操作系统而异），从源代码中的 JSON 文件。

机密密钥管理器工具设置分为 UserSecretsId 属性使用机密的项目。 因此，你必须确保在项目文件 （如下面的代码段中所示） 中设置 UserSecretsId 属性。 用作 ID 的实际字符串并不重要，只要它是唯一项目中。

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

使用使用密钥管理器中存储应用程序中的机密通过调用 AddUserSecrets&lt;T&gt; ConfigurationBuilder 实例要包含在其配置中的机密信息，以便应用程序上。 泛型参数 T 应 UserSecretId 被应用到的程序集中的类型。 通常使用 AddUserSecrets&lt;启动&gt;属正常情况。


>[!div class="step-by-step"]
[以前](授权-net-微服务-web-applications.md) [下一步] (azure 的密钥-保管库的保护-secrets.md)
