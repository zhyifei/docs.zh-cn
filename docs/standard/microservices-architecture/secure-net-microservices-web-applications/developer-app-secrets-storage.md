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
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="ec586-103">在开发过程中安全地存储应用程序机密</span><span class="sxs-lookup"><span data-stu-id="ec586-103">Storing application secrets safely during development</span></span>

<span data-ttu-id="ec586-104">若要连接受保护的资源和其他服务，ASP.NET Core 应用程序通常需要使用包含敏感信息的连接字符串、密码或其他凭据。</span><span class="sxs-lookup"><span data-stu-id="ec586-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="ec586-105">这些敏感的信息片段被称为“机密”。</span><span class="sxs-lookup"><span data-stu-id="ec586-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="ec586-106">最好不要在源代码中包含机密，当然也不要在源代码管理中存储机密。</span><span class="sxs-lookup"><span data-stu-id="ec586-106">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="ec586-107">相反，应使用 ASP.NET Core 配置模型从更安全的位置读取机密。</span><span class="sxs-lookup"><span data-stu-id="ec586-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="ec586-108">应将用于访问开发和暂存资源的机密与用于访问生产资源的机密分开，因为不同的个人需要访问不同的机密集。</span><span class="sxs-lookup"><span data-stu-id="ec586-108">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="ec586-109">若要存储在开发过程中使用的机密，常用的方法是在环境变量中或通过使用 ASP.NET Core 机密管理器工具存储机密。</span><span class="sxs-lookup"><span data-stu-id="ec586-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="ec586-110">为了在生产环境中实现更安全的存储，微服务可以将机密存储在 Azure Key Vault 中。</span><span class="sxs-lookup"><span data-stu-id="ec586-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="ec586-111">在环境变量中存储机密</span><span class="sxs-lookup"><span data-stu-id="ec586-111">Storing secrets in environment variables</span></span>

<span data-ttu-id="ec586-112">在源代码外部保存机密的一种方法是，开发者将基于字符串的机密设置为开发计算机上的[环境变量](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables)。</span><span class="sxs-lookup"><span data-stu-id="ec586-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="ec586-113">当使用环境变量来存储具有层次结构名称（嵌套在配置节中的名称）的机密时，为环境变量（包含机密名称的完整层次结构）创建一个名称，并用冒号 (:) 分隔。</span><span class="sxs-lookup"><span data-stu-id="ec586-113">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="ec586-114">例如，将环境变量 Logging:LogLevel:Default 设置为 Debug 将等效于以下 JSON 文件中的配置值：</span><span class="sxs-lookup"><span data-stu-id="ec586-114">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="ec586-115">若要从环境变量访问这些值，应用程序只需在构造 IConfigurationRoot 对象时调用其 ConfigurationBuilder 上的 AddEnvironmentVariables。</span><span class="sxs-lookup"><span data-stu-id="ec586-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="ec586-116">请注意，环境变量通常以纯文本形式存储，因此，如果计算机或带有环境变量的进程受到破坏，环境变量值将可见。</span><span class="sxs-lookup"><span data-stu-id="ec586-116">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="ec586-117">使用 ASP.NET Core 机密管理器存储机密</span><span class="sxs-lookup"><span data-stu-id="ec586-117">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="ec586-118">ASP.NET Core [机密管理器](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager)工具提供了在源代码外部保存机密的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="ec586-118">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="ec586-119">若要使用“机密管理器”工具，请在项目文件中包含 Microsoft.Extensions.SecretManager.Tools 包的工具参考 (DotNetCliToolReference)。</span><span class="sxs-lookup"><span data-stu-id="ec586-119">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="ec586-120">一旦出现并恢复了该依赖关系，就可以使用 dotnet 用户机密命令来设置命令行中的机密值。</span><span class="sxs-lookup"><span data-stu-id="ec586-120">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="ec586-121">这些机密将存储在用户配置文件目录中的 JSON 文件中（详细信息随操作系统而异），与源代码无关。</span><span class="sxs-lookup"><span data-stu-id="ec586-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="ec586-122">机密管理器工具设置的机密是由使用机密的项目的 UserSecretsId 属性组织的。</span><span class="sxs-lookup"><span data-stu-id="ec586-122">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="ec586-123">因此，必须确保在项目文件（如下面的代码片段所示）中设置 UserSecretsId 属性。</span><span class="sxs-lookup"><span data-stu-id="ec586-123">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="ec586-124">用作 ID 的实际字符串并不重要，只要它在项目中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ec586-124">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="ec586-125">通过调用 ConfigurationBuilder 实例上的 AddUserSecrets&lt;T&gt; 将应用程序的机密包含在其配置中，就可以在应用程序中使用通过机密管理器存储的机密。</span><span class="sxs-lookup"><span data-stu-id="ec586-125">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="ec586-126">泛型参数 T 应是 UserSecretId 应用到的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="ec586-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="ec586-127">通常可以使用 AddUserSecrets&lt;Startup&gt;。</span><span class="sxs-lookup"><span data-stu-id="ec586-127">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="ec586-128">[上一篇] (authorization-net-microservices-web-applications.md) [下一篇] (azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="ec586-128">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
