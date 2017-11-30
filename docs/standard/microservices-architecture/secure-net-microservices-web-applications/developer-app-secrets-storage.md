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
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="cb1b3-104">在开发过程中安全地存储应用程序机密</span><span class="sxs-lookup"><span data-stu-id="cb1b3-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="cb1b3-105">若要连接与受保护的资源和其他服务，ASP.NET Core 应用程序通常需要使用连接字符串、 密码或包含敏感信息的其他凭据。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="cb1b3-106">这些敏感的信息片段称为*机密*。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="cb1b3-107">它是一种最佳做法不在源代码中包含机密而肯定不是存储在源代码管理中的机密。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="cb1b3-108">相反，应使用 ASP.NET Core 配置模型从更安全的位置读取的机密。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="cb1b3-109">你应将分开的机密访问开发和过渡与用于访问生产资源，因为不同的个人需要对这些不同的机密集的访问的资源。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="cb1b3-110">若要存储在开发过程中使用的机密，常用的方法是在环境变量中或通过使用 ASP.NET 核心机密 Manager 工具或者存储机密信息。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="cb1b3-111">有关在生产环境中的更安全存储，微服务可以在 Azure 密钥保管库存储机密。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="cb1b3-112">在环境变量中存储机密</span><span class="sxs-lookup"><span data-stu-id="cb1b3-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="cb1b3-113">保留源代码之外的机密的一种方法是为开发人员设置基于字符串的机密作为[环境变量](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables)在其开发计算机上。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="cb1b3-114">当使用环境变量来存储具有层次结构名称 （那些嵌套在配置节中） 的机密，创建一个环境变量的名称，包含机密的名称的完整层次结构时，用冒号 （:） 分隔。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="cb1b3-115">例如，将日志记录： LogLevel:Default 的环境变量设置为调试将等效于配置值从下面的 JSON 文件：</span><span class="sxs-lookup"><span data-stu-id="cb1b3-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="cb1b3-116">若要从环境变量访问这些值，应用程序只需在其 ConfigurationBuilder 上调用 AddEnvironmentVariables 构造 IConfigurationRoot 对象时。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="cb1b3-117">请注意，环境变量通常存储为纯文本，因此，如果计算机或使用环境变量的进程受到攻击，环境变量值将会可见。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="cb1b3-118">存储机密使用 ASP.NET 核心机密管理器</span><span class="sxs-lookup"><span data-stu-id="cb1b3-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="cb1b3-119">ASP.NET 核心[机密 Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager)工具提供了另一种方法来保留源代码之外的机密。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="cb1b3-120">若要使用密码管理器工具，包括你的项目文件中的 Microsoft.Extensions.SecretManager.Tools 包工具参考 (DotNetCliToolReference)。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="cb1b3-121">一旦该依赖关系存在并已还原，dotnet 用户机密命令可以用于从命令行设置机密的值。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="cb1b3-122">这些机密将存储在用户的配置文件目录 （详细信息因操作系统而异），从源代码中的 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="cb1b3-123">机密密钥管理器工具设置分为 UserSecretsId 属性使用机密的项目。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="cb1b3-124">因此，你必须确保在项目文件 （如下面的代码段中所示） 中设置 UserSecretsId 属性。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="cb1b3-125">用作 ID 的实际字符串并不重要，只要它是唯一项目中。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="cb1b3-126">使用使用密钥管理器中存储应用程序中的机密通过调用 AddUserSecrets&lt;T&gt; ConfigurationBuilder 实例要包含在其配置中的机密信息，以便应用程序上。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="cb1b3-127">泛型参数 T 应 UserSecretId 被应用到的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="cb1b3-128">通常使用 AddUserSecrets&lt;启动&gt;属正常情况。</span><span class="sxs-lookup"><span data-stu-id="cb1b3-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="cb1b3-129">[以前](授权-net-微服务-web-applications.md) [下一步] (azure 的密钥-保管库的保护-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="cb1b3-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
