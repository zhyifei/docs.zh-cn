---
title: "何时选择 Docker 容器中的.NET Framework"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |何时选择 Docker 容器中的.NET Framework"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 1bf1f055f040e7f3dc575b7a04140ebf0c599f98
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a><span data-ttu-id="9a749-104">何时选择 Docker 容器中的.NET Framework</span><span class="sxs-lookup"><span data-stu-id="9a749-104">When to choose .NET Framework for Docker containers</span></span>

<span data-ttu-id="9a749-105">虽然.NET 核心提供显著的好处，为新的应用程序和应用程序模式，.NET Framework 将持续成为适合于许多现有方案。</span><span class="sxs-lookup"><span data-stu-id="9a749-105">While .NET Core offers significant benefits for new applications and application patterns, .NET Framework will continue to be a good choice for many existing scenarios.</span></span>

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a><span data-ttu-id="9a749-106">迁移现有应用程序直接到 Windows Server 容器</span><span class="sxs-lookup"><span data-stu-id="9a749-106">Migrating existing applications directly to a Windows Server container</span></span>

<span data-ttu-id="9a749-107">你可能想要使用 Docker 容器只是为了简化部署，即使你不在创建微服务。</span><span class="sxs-lookup"><span data-stu-id="9a749-107">You might want to use Docker containers just to simplify deployment, even if you are not creating microservices.</span></span> <span data-ttu-id="9a749-108">例如，可能是你想要提高你 DevOps 工作流使用 Docker，容器可以为你提供更好地隔离的测试环境，并还可以消除引起缺少的依赖关系，你将移动到生产环境时的部署问题。</span><span class="sxs-lookup"><span data-stu-id="9a749-108">For example, perhaps you want to improve your DevOps workflow with Docker—containers can give you better isolated test environments and can also eliminate deployment issues caused by missing dependencies when you move to a production environment.</span></span> <span data-ttu-id="9a749-109">在类似这样的情况下，即使你要部署的整体应用程序，最好为当前.NET Framework 应用程序中使用 Docker 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="9a749-109">In cases like these, even if you are deploying a monolithic application, it makes sense to use Docker and Windows Containers for your current .NET Framework applications.</span></span>

<span data-ttu-id="9a749-110">在大多数情况下，对于这种情况下，将不需要迁移到.NET 核心; 的现有应用程序你可以使用包括传统的.NET Framework 的 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="9a749-110">In most cases for this scenario, you will not need to migrate your existing applications to .NET Core; you can use Docker containers that include the traditional .NET Framework.</span></span> <span data-ttu-id="9a749-111">但是，建议的方法是使用.NET 核心扩展现有的应用程序，例如，在 ASP.NET 核心中写入新的服务。</span><span class="sxs-lookup"><span data-stu-id="9a749-111">However, a recommended approach is to use .NET Core as you extend an existing application, such as writing a new service in ASP.NET Core.</span></span>

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a><span data-ttu-id="9a749-112">为.NET 核心使用第三方.NET 库或不可用的 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="9a749-112">Using third-party .NET libraries or NuGet packages not available for .NET Core</span></span>

<span data-ttu-id="9a749-113">第三方库快速开始采用[.NET 标准](https://docs.microsoft.com/dotnet/standard/net-standard)，这可使在各种.NET 版本，包括.NET 核心之间共享的代码。</span><span class="sxs-lookup"><span data-stu-id="9a749-113">Third-party libraries are quickly embracing the [.NET Standard](https://docs.microsoft.com/dotnet/standard/net-standard), which enables code sharing across all .NET flavors, including .NET Core.</span></span> <span data-ttu-id="9a749-114">.NET 标准库 2.0 和更高版本的 API 图面跨不同的框架的兼容性变得明显更大，.NET 核心 2.0 中应用程序还可以直接引用现有的.NET Framework 库 (请参阅[compat填充码](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work))。</span><span class="sxs-lookup"><span data-stu-id="9a749-114">With the .NET Standard Library 2.0 and beyond the API surface compatibility across different frameworks has become significantly larger and in .NET Core 2.0 applications can also directly reference existing .NET Framework libraries (see [compat shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).</span></span>

<span data-ttu-id="9a749-115">但是，即使使用由于.NET 标准 2.0 和.NET 核心 2.0 该异常前进，可能有情况下，其中某些 NuGet 包需要 Windows 运行，但可能不支持.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="9a749-115">However, even with that exceptional progression since .NET Standard 2.0 and .NET Core 2.0, there might be cases where certain NuGet packages need Windows to run and might not support .NET Core.</span></span> <span data-ttu-id="9a749-116">如果这些包都是关键应用程序，你将需要在 Windows 容器上使用.NET Framework。</span><span class="sxs-lookup"><span data-stu-id="9a749-116">If those packages are critical for your application, then you will need to use .NET Framework on Windows Containers.</span></span>

## <a name="usingnet-technologies-not-available-for-net-core"></a><span data-ttu-id="9a749-117">不可用于.NET 核心的 Using.NET 技术</span><span class="sxs-lookup"><span data-stu-id="9a749-117">Using.NET technologies not available for .NET Core</span></span> 

<span data-ttu-id="9a749-118">某些.NET Framework 技术将不可用.NET 核心 （撰写本文时版本 2.0） 的当前版本中。</span><span class="sxs-lookup"><span data-stu-id="9a749-118">Some .NET Framework technologies are not available in the current version of .NET Core (version 2.0 as of this writing).</span></span> <span data-ttu-id="9a749-119">其中一些可在更高版本的.NET Core 版本 (.NET 核心 2.x)，但其他不适用于新的应用程序模式针对.NET Core 和可能永远不能使用。</span><span class="sxs-lookup"><span data-stu-id="9a749-119">Some of them will be available in later .NET Core releases (.NET Core 2.x), but others do not apply to the new application patterns targeted by .NET Core and might never be available.</span></span>

<span data-ttu-id="9a749-120">以下列表显示在.NET 核心 2.0 中不可用的技术的大多数：</span><span class="sxs-lookup"><span data-stu-id="9a749-120">The following list shows most of the technologies that are not available in .NET Core 2.0:</span></span>

-   <span data-ttu-id="9a749-121">ASP.NET Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="9a749-121">ASP.NET Web Forms.</span></span> <span data-ttu-id="9a749-122">仅在.NET Framework 上提供了此技术。</span><span class="sxs-lookup"><span data-stu-id="9a749-122">This technology is only available on .NET Framework.</span></span> <span data-ttu-id="9a749-123">目前没有将 ASP.NET Web 窗体引入 .NET Core 的计划。</span><span class="sxs-lookup"><span data-stu-id="9a749-123">Currently there are no plans to bring ASP.NET Web Forms to .NET Core.</span></span>

-   <span data-ttu-id="9a749-124">WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="9a749-124">WCF services.</span></span> <span data-ttu-id="9a749-125">即使[WCF 客户端库](https://github.com/dotnet/wcf)可使用从.NET 核心的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="9a749-125">Even when a [WCF-Client library](https://github.com/dotnet/wcf) is available to consume WCF services from .NET Core.</span></span> <span data-ttu-id="9a749-126">截至中旬 2017 WCF 服务器实现仅在.NET Framework 上可用。</span><span class="sxs-lookup"><span data-stu-id="9a749-126">as of mid-2017, the WCF server implementation is only available on .NET Framework.</span></span> <span data-ttu-id="9a749-127">这种情况下可视为针对将来版本的.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="9a749-127">This scenario might be considered for future releases of .NET Core.</span></span>

-   <span data-ttu-id="9a749-128">与工作流相关的服务。</span><span class="sxs-lookup"><span data-stu-id="9a749-128">Workflow-related services.</span></span> <span data-ttu-id="9a749-129">Windows Workflow Foundation (WF)、 工作流服务 （WCF + WF 中单个服务） 和 WCF 数据服务 （以前称为 ADO.NET Data Services） 才在.NET Framework 上可用。</span><span class="sxs-lookup"><span data-stu-id="9a749-129">Windows Workflow Foundation (WF), Workflow Services (WCF + WF in a single service), and WCF Data Services (formerly known as ADO.NET Data Services) are only available on .NET Framework.</span></span> <span data-ttu-id="9a749-130">目前没有计划，以使它们到.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="9a749-130">There are currently no plans to bring them to .NET Core.</span></span>

<span data-ttu-id="9a749-131">除了技术之外列入官方[.NET 核心路线图](https://github.com/aspnet/Home/wiki/Roadmap)，其他功能可能移植到.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="9a749-131">In addition to the technologies listed in the official [.NET Core roadmap](https://github.com/aspnet/Home/wiki/Roadmap), other features might be ported to .NET Core.</span></span> <span data-ttu-id="9a749-132">有关完整列表，查看的项标记为[端口核心](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core)CoreFX GitHub 站点上。</span><span class="sxs-lookup"><span data-stu-id="9a749-132">For a full list, look at the items tagged as [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) on the CoreFX GitHub site.</span></span> <span data-ttu-id="9a749-133">请注意，此列表不表示从 Microsoft 的承诺，以使这些组件进入.NET 核心 — 项只需捕获来自社区的请求。</span><span class="sxs-lookup"><span data-stu-id="9a749-133">Note that this list does not represent a commitment from Microsoft to bring those components to .NET Core—the items simply capture requests from the community.</span></span> <span data-ttu-id="9a749-134">如果您关心任何上面列出的组件，请考虑参与 GitHub 上的讨论，以便可以听到您的声音。</span><span class="sxs-lookup"><span data-stu-id="9a749-134">If you care about any of the components listed above, consider participating in the discussions on GitHub so that your voice can be heard.</span></span> <span data-ttu-id="9a749-135">如果认为丢失了某些内容，请[在 CoreFX 存储库中提出新的问题](https://github.com/dotnet/corefx/issues/new)。</span><span class="sxs-lookup"><span data-stu-id="9a749-135">And if you think something is missing, please [file a new issue in the CoreFX repository](https://github.com/dotnet/corefx/issues/new).</span></span>

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a><span data-ttu-id="9a749-136">使用平台或不支持.NET 核心的 API</span><span class="sxs-lookup"><span data-stu-id="9a749-136">Using a platform or API that does not support .NET Core</span></span>

<span data-ttu-id="9a749-137">某些 Microsoft 或第三方平台不支持.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="9a749-137">Some Microsoft or third-party platforms do not support .NET Core.</span></span> <span data-ttu-id="9a749-138">例如，某些 Azure 服务提供尚不可用在.NET Core 上使用的 SDK。</span><span class="sxs-lookup"><span data-stu-id="9a749-138">For example, some Azure services provide an SDK that is not yet available for consumption on .NET Core.</span></span> <span data-ttu-id="9a749-139">这是临时的因为所有 Azure 服务最终将使用.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="9a749-139">This is temporary, because all Azure services will eventually use .NET Core.</span></span> <span data-ttu-id="9a749-140">例如， [Azure DocumentDB SDK for.NET 核心](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1)发布为预览在 2016 年 11 月 16 日，但它现在是稳定的版本为正式版 (GA)。</span><span class="sxs-lookup"><span data-stu-id="9a749-140">For example, the [Azure DocumentDB SDK for .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) was released as a preview on November 16, 2016, but it is now generally available (GA) as a stable version.</span></span>

<span data-ttu-id="9a749-141">在此期间，如果任何平台或在 Azure 中的服务仍不支持.NET 核心使用其客户端 API，你可以在.NET Framework 上使用等效的 REST API 从 Azure 服务或客户端 SDK。</span><span class="sxs-lookup"><span data-stu-id="9a749-141">In the meantime, if any platform or service in Azure still doesn’t support .NET Core with its client API, you can use the equivalent REST API from the Azure service or the client SDK on .NET Framework.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="9a749-142">其他资源</span><span class="sxs-lookup"><span data-stu-id="9a749-142">Additional resources</span></span>

-   <span data-ttu-id="9a749-143">**.NET 核心指南**
    [*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)</span><span class="sxs-lookup"><span data-stu-id="9a749-143">**.NET Core Guide**
[*https://docs.microsoft.com/dotnet/core/index*](https://docs.microsoft.com/dotnet/core/index)</span></span>

-   <span data-ttu-id="9a749-144">**从.NET Framework 移植到.NET 核心**
    [*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)</span><span class="sxs-lookup"><span data-stu-id="9a749-144">**Porting from .NET Framework to .NET Core**
[*https://docs.microsoft.com/dotnet/core/porting/index*](https://docs.microsoft.com/dotnet/core/porting/index)</span></span>

-   <span data-ttu-id="9a749-145">**.NET framework 在 Docker 指南上的**
    [*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)</span><span class="sxs-lookup"><span data-stu-id="9a749-145">**.NET Framework on Docker Guide**
[*https://docs.microsoft.com/dotnet/framework/docker/*](https://docs.microsoft.com/dotnet/framework/docker/)</span></span>

-   <span data-ttu-id="9a749-146">**.NET 组件概述**
    [*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)</span><span class="sxs-lookup"><span data-stu-id="9a749-146">**.NET Components Overview**
[*https://docs.microsoft.com/dotnet/standard/components*](https://docs.microsoft.com/dotnet/standard/components)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="9a749-147">[以前](net-核心-容器-scenarios.md) [下一步] (容器-framework-选择-factors.md)</span><span class="sxs-lookup"><span data-stu-id="9a749-147">[Previous] (net-core-container-scenarios.md) [Next] (container-framework-choice-factors.md)</span></span>
