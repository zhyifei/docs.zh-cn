---
title: 在开发过程中安全地存储应用程序机密
description: .Net 微服务和 Web 应用程序中的安全性 - 不要在源代码管理中存储密码、连接字符串或 API 密钥等应用程序机密，了解在 ASP.NET Core 中可以使用的选项，特别是必须了解如何处理“用户机密”。
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: fe8e7fa11c9a4f4cae133c2e09f9e4b4dd40a546
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "54361984"
---
# <a name="store-application-secrets-safely-during-development"></a><span data-ttu-id="f6617-103">在开发过程中安全地存储应用程序机密</span><span class="sxs-lookup"><span data-stu-id="f6617-103">Store application secrets safely during development</span></span>

<span data-ttu-id="f6617-104">若要连接受保护的资源和其他服务，ASP.NET Core 应用程序通常需要使用包含敏感信息的连接字符串、密码或其他凭据。</span><span class="sxs-lookup"><span data-stu-id="f6617-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="f6617-105">这些敏感的信息片段被称为“机密”。</span><span class="sxs-lookup"><span data-stu-id="f6617-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="f6617-106">最好不要在源代码中包含机密，并确保不要在源代码管理中存储机密。</span><span class="sxs-lookup"><span data-stu-id="f6617-106">It's a best practice to not include secrets in source code and making sure not to store secrets in source control.</span></span> <span data-ttu-id="f6617-107">相反，应使用 ASP.NET Core 配置模型从更安全的位置读取机密。</span><span class="sxs-lookup"><span data-stu-id="f6617-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="f6617-108">必须将用于访问开发和暂存资源的机密与用于访问生产资源的机密分开，因为不同的个人需要访问不同的机密集。</span><span class="sxs-lookup"><span data-stu-id="f6617-108">You must separate the secrets for accessing development and staging resources from the ones used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="f6617-109">若要存储在开发过程中使用的机密，常用的方法是在环境变量中或通过使用 ASP.NET Core 机密管理器工具存储机密。</span><span class="sxs-lookup"><span data-stu-id="f6617-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="f6617-110">为了在生产环境中实现更安全的存储，微服务可以将机密存储在 Azure Key Vault 中。</span><span class="sxs-lookup"><span data-stu-id="f6617-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="store-secrets-in-environment-variables"></a><span data-ttu-id="f6617-111">在环境变量中存储机密</span><span class="sxs-lookup"><span data-stu-id="f6617-111">Store secrets in environment variables</span></span>

<span data-ttu-id="f6617-112">在源代码外部保存机密的一种方法是，开发者将基于字符串的机密设置为开发计算机上的[环境变量](/aspnet/core/security/app-secrets#environment-variables)。</span><span class="sxs-lookup"><span data-stu-id="f6617-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="f6617-113">当使用环境变量来存储具有层次结构名称（如嵌套在配置节中的名称）的机密时，必须为这些变量命名，以包含其各节的完整层次结构，并用冒号 (:) 分隔。</span><span class="sxs-lookup"><span data-stu-id="f6617-113">When you use environment variables to store secrets with hierarchical names, such as the ones nested in configuration sections, you must name the variables to include the complete hierarchy of its sections, delimited with colons (:).</span></span>

<span data-ttu-id="f6617-114">例如，将环境变量 `Logging:LogLevel:Default` 设置为 `Debug` 值将等效于以下 JSON 文件中的配置值：</span><span class="sxs-lookup"><span data-stu-id="f6617-114">For example, setting an environment variable `Logging:LogLevel:Default` to `Debug` value would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="f6617-115">若要从环境变量访问这些值，应用程序只需在构造 IConfigurationRoot 对象时调用其 ConfigurationBuilder 上的 AddEnvironmentVariables。</span><span class="sxs-lookup"><span data-stu-id="f6617-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="f6617-116">请注意，环境变量通常以纯文本形式存储，因此，如果计算机或带有环境变量的进程受到破坏，环境变量值将可见。</span><span class="sxs-lookup"><span data-stu-id="f6617-116">Note that environment variables are commonly stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a><span data-ttu-id="f6617-117">使用 ASP.NET Core 机密管理器存储机密</span><span class="sxs-lookup"><span data-stu-id="f6617-117">Store secrets with the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="f6617-118">ASP.NET Core [机密管理器](/aspnet/core/security/app-secrets#secret-manager)工具提供了在源代码外部保存机密的另一种方法。</span><span class="sxs-lookup"><span data-stu-id="f6617-118">The ASP.NET Core [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="f6617-119">若要使用机密管理器工具，请在项目文件中安装包 Microsoft.Extensions.Configuration.SecretManager。</span><span class="sxs-lookup"><span data-stu-id="f6617-119">To use the Secret Manager tool, install the package **Microsoft.Extensions.Configuration.SecretManager** in your project file.</span></span> <span data-ttu-id="f6617-120">如果该依赖项存在并且已还原，则可以使用 `dotnet user-secrets` 命令来通过命令行设置机密的值。</span><span class="sxs-lookup"><span data-stu-id="f6617-120">Once that dependency is present and has been restored, the `dotnet user-secrets` command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="f6617-121">这些机密将存储在用户配置文件目录中的 JSON 文件中（详细信息随操作系统而异），与源代码无关。</span><span class="sxs-lookup"><span data-stu-id="f6617-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="f6617-122">机密管理器工具设置的机密是由使用机密的项目的 `UserSecretsId` 属性组织的。</span><span class="sxs-lookup"><span data-stu-id="f6617-122">Secrets set by the Secret Manager tool are organized by the `UserSecretsId` property of the project that's using the secrets.</span></span> <span data-ttu-id="f6617-123">因此，必须确保在项目文件中设置 UserSecretsId 属性，如下面的代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="f6617-123">Therefore, you must be sure to set the UserSecretsId property in your project file, as shown in the snippet below.</span></span> <span data-ttu-id="f6617-124">默认值是 Visual Studio 分配的 GUID，但实际字符串并不重要，只要它在计算机中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f6617-124">The default value is a GUID assigned by Visual Studio, but the actual string is not important as long as it's unique in your computer.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="f6617-125">通过调用 ConfigurationBuilder 实例上的 `AddUserSecrets<T>` 将应用程序的机密包含在其配置中，就可以在应用程序中使用通过机密管理器存储的机密。</span><span class="sxs-lookup"><span data-stu-id="f6617-125">Using secrets stored with Secret Manager in an application is accomplished by calling `AddUserSecrets<T>` on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="f6617-126">泛型参数 T 应是 UserSecretId 应用到的程序集中的类型。</span><span class="sxs-lookup"><span data-stu-id="f6617-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="f6617-127">通常使用 `AddUserSecrets<Startup>` 没问题。</span><span class="sxs-lookup"><span data-stu-id="f6617-127">Usually using `AddUserSecrets<Startup>` is fine.</span></span>

<span data-ttu-id="f6617-128">在 Program.cs 中使用 `CreateDefaultBuilder` 方法时，`AddUserSecrets<Startup>()` 包含在开发环境的默认选项中。</span><span class="sxs-lookup"><span data-stu-id="f6617-128">The `AddUserSecrets<Startup>()` is included in the default options for the Development environment when using the `CreateDefaultBuilder` method in *Program.cs*.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f6617-129">[上一页](authorization-net-microservices-web-applications.md)
>[下一页](azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="f6617-129">[Previous](authorization-net-microservices-web-applications.md)
[Next](azure-key-vault-protects-secrets.md)</span></span>
