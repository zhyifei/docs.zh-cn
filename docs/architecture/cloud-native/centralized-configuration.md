---
title: 集中式配置
description: 使用 Azure Key Vault 进行集中配置可以更轻松地管理云本机应用。
ms.date: 06/30/2019
ms.openlocfilehash: 4c516b6773d913acd71ff06742302e9766a141e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841137"
---
# <a name="centralized-configuration"></a><span data-ttu-id="bc8b9-103">集中式配置</span><span class="sxs-lookup"><span data-stu-id="bc8b9-103">Centralized configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bc8b9-104">与传统的单实例应用程序相比，云本机应用程序需要运行更多的服务。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-104">Cloud-native applications involve many more running services than traditional single-instance monolithic apps.</span></span> <span data-ttu-id="bc8b9-105">管理数十个相互依赖的服务的配置设置可能很困难，这就是通常为分布式应用程序实现集中式配置存储的原因。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-105">Managing configuration settings for dozens of interdependent services can be challenging, which is why centralized configuration stores are often implemented for distributed applications.</span></span>

<span data-ttu-id="bc8b9-106">如[第1章](introduction.md)所述，十二因素应用建议要求严格分隔代码和配置。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-106">As discussed in [Chapter 1](introduction.md), the Twelve-Factor App recommendations require strict separation between code and configuration.</span></span> <span data-ttu-id="bc8b9-107">这意味着，将配置设置存储为代码中的常量或文本值是一个冲突。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-107">This means storing configuration settings as constants or literal values in code is a violation.</span></span> <span data-ttu-id="bc8b9-108">存在此建议是因为应跨多个环境（包括开发、测试、暂存和生产）使用相同的代码。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-108">This recommendation exists because the same code should be used across multiple environments, including development, testing, staging, and production.</span></span> <span data-ttu-id="bc8b9-109">但是，每个环境中的配置值可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-109">However, configuration values are likely to vary between each of these environments.</span></span> <span data-ttu-id="bc8b9-110">因此，配置值应存储在环境本身中，否则环境应将凭据存储到集中式配置存储中。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-110">So, configuration values should be stored in the environment itself, or the environment should store the credentials to a centralized configuration store.</span></span>

<span data-ttu-id="bc8b9-111">EShopOnContainers 应用程序包含每个微服务的本地应用程序设置文件。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-111">The eShopOnContainers application includes local application settings files with each microservice.</span></span> <span data-ttu-id="bc8b9-112">这些文件签入到源代码管理中，但不包括诸如连接字符串或 API 密钥之类的生产机密。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-112">These files are checked into source control but don't include production secrets such as connection strings or API keys.</span></span> <span data-ttu-id="bc8b9-113">在生产环境中，可能会覆盖每个服务环境变量的各个设置。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-113">In production, individual settings may be overwritten with per-service environment variables.</span></span> <span data-ttu-id="bc8b9-114">这种做法通常适用于托管应用程序，但不提供中央配置存储。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-114">This is a common practice for hosted applications, but doesn't provide a central configuration store.</span></span> <span data-ttu-id="bc8b9-115">为了支持集中管理的配置设置，每个微服务都包含一个设置以在其使用本地设置或 Azure Key Vault 设置之间切换。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-115">To support centralized management of configuration settings, each microservice includes a setting to toggle between its use of local settings or Azure Key Vault settings.</span></span>

## <a name="azure-key-vault"></a><span data-ttu-id="bc8b9-116">Azure 密钥保管库</span><span class="sxs-lookup"><span data-stu-id="bc8b9-116">Azure Key Vault</span></span>

<span data-ttu-id="bc8b9-117">Azure Key Vault 提供令牌、密码、证书、API 密钥和其他敏感机密的安全存储。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-117">Azure Key Vault provides secure storage of tokens, passwords, certificates, API keys, and other sensitive secrets.</span></span> <span data-ttu-id="bc8b9-118">访问 Key Vault 需要正确的调用方身份验证和授权，在这种情况下，eShopOnContainers 微服务意味着使用 ClientId/ClientSecret 组合。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-118">Access to Key Vault requires proper caller authentication and authorization, which in the case of the eShopOnContainers microservices means the use of a ClientId/ClientSecret combination.</span></span> <span data-ttu-id="bc8b9-119">请勿将这些凭据签入源控件，而是在应用程序的环境中进行设置。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-119">Don't check in these credentials into source control, but instead set in the application's environment.</span></span> <span data-ttu-id="bc8b9-120">使用[Key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol)可以实现从 AKS 的直接访问 Key Vault。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-120">Direct access to Key Vault from AKS can be achieved using [Key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol).</span></span>

<span data-ttu-id="bc8b9-121">使用集中式配置，适用于整个应用程序的设置（例如集中式日志记录终结点）只能设置一次，并由分布式应用程序的每个部分使用。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-121">With centralized configuration, settings that apply to the entire application, such as the centralized logging endpoint, can be set once and used by every part of the distributed application.</span></span> <span data-ttu-id="bc8b9-122">尽管微服务应该彼此独立，但通常仍有一些共享依赖项，其配置详细信息可从集中式配置存储中获益。</span><span class="sxs-lookup"><span data-stu-id="bc8b9-122">Although microservices should be independent of one another, there will typically still be some shared dependencies whose configuration details can benefit from a centralized configuration store.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bc8b9-123">[上一页](deploy-eshoponcontainers-azure.md)
>[下一页](scale-applications.md)</span><span class="sxs-lookup"><span data-stu-id="bc8b9-123">[Previous](deploy-eshoponcontainers-azure.md)
[Next](scale-applications.md)</span></span>
