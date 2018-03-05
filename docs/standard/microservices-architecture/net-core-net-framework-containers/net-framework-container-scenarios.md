---
title: "何时为 Docker 容器选择 .NET Framework"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 何时为 Docker 容器选择 .NET Framework"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: eec258ff01bcfeb834fa7a1138fdf822fd00c996
ms.sourcegitcommit: c3957fdb990060559d73cca44ab3e2c7b4d049c0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2018
---
# <a name="when-to-choose-net-framework-for-docker-containers"></a><span data-ttu-id="83620-104">何时为 Docker 容器选择 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="83620-104">When to choose .NET Framework for Docker containers</span></span>

<span data-ttu-id="83620-105">虽然 .NET Core 为新的应用程序和应用程序模式带来的好处很明显，但在很多现有情况下仍然会选择 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="83620-105">While .NET Core offers significant benefits for new applications and application patterns, .NET Framework will continue to be a good choice for many existing scenarios.</span></span>

## <a name="migrating-existing-applications-directly-to-a-windows-server-container"></a><span data-ttu-id="83620-106">将现有应用程序直接迁移到 Windows Server 容器</span><span class="sxs-lookup"><span data-stu-id="83620-106">Migrating existing applications directly to a Windows Server container</span></span>

<span data-ttu-id="83620-107">你可能只想使用 Docker 容器来简化部署（即便未创建微服务）。</span><span class="sxs-lookup"><span data-stu-id="83620-107">You might want to use Docker containers just to simplify deployment, even if you are not creating microservices.</span></span> <span data-ttu-id="83620-108">例如，你可能希望使用 Docker 改进 DevOps 工作流 — 容器可以提供更好的独立测试环境，并且还可以消除在迁移到生产环境时由于缺少依赖关系而导致的部署问题。</span><span class="sxs-lookup"><span data-stu-id="83620-108">For example, perhaps you want to improve your DevOps workflow with Docker—containers can give you better isolated test environments and can also eliminate deployment issues caused by missing dependencies when you move to a production environment.</span></span> <span data-ttu-id="83620-109">在这种情况下，即使部署的是整体式应用程序，也可以为当前的 .NET Framework 应用程序使用 Docker 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="83620-109">In cases like these, even if you are deploying a monolithic application, it makes sense to use Docker and Windows Containers for your current .NET Framework applications.</span></span>

<span data-ttu-id="83620-110">对于此方案，大多数情况下无需将现有应用程序迁移到 .NET Core；可以使用包含传统 .NET Framework 的 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="83620-110">In most cases for this scenario, you will not need to migrate your existing applications to .NET Core; you can use Docker containers that include the traditional .NET Framework.</span></span> <span data-ttu-id="83620-111">不过，在扩展现有的应用程序（例如，在 ASP.NET Core 中编写新服务）时，建议使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="83620-111">However, a recommended approach is to use .NET Core as you extend an existing application, such as writing a new service in ASP.NET Core.</span></span>

## <a name="using-third-party-net-libraries-or-nuget-packages-not-available-for-net-core"></a><span data-ttu-id="83620-112">使用不可用于 .NET Core 的第三方 .NET 库或 NuGet 包</span><span class="sxs-lookup"><span data-stu-id="83620-112">Using third-party .NET libraries or NuGet packages not available for .NET Core</span></span>

<span data-ttu-id="83620-113">第三方库正在迅速采用 [.NET Standard](../../net-standard.md)，这样可跨各种 .NET 版本（包括 .NET Core）共享代码。</span><span class="sxs-lookup"><span data-stu-id="83620-113">Third-party libraries are quickly embracing the [.NET Standard](../../net-standard.md), which enables code sharing across all .NET flavors, including .NET Core.</span></span> <span data-ttu-id="83620-114">在 .NET Standard 库 2.0 及更高版本中，跨不同框架的 API 表面兼容性变得更加庞大；在 .NET Core 2.0 中，应用程序还可以直接引用现有的 .NET Framework 库（请参阅[兼容性填充程序](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)）。</span><span class="sxs-lookup"><span data-stu-id="83620-114">With the .NET Standard Library 2.0 and beyond the API surface compatibility across different frameworks has become significantly larger and in .NET Core 2.0 applications can also directly reference existing .NET Framework libraries (see [compat shim](https://github.com/dotnet/standard/blob/master/docs/faq.md#how-does-net-standard-versioning-work)).</span></span>

<span data-ttu-id="83620-115">但即使 .NET Standard 2.0 和 .NET Core 2.0 取得了如此重大的进展，也可能出现某些 NuGet 包需要在 Windows 上运行并且可能不支持 .NET Core 的情况。</span><span class="sxs-lookup"><span data-stu-id="83620-115">However, even with that exceptional progression since .NET Standard 2.0 and .NET Core 2.0, there might be cases where certain NuGet packages need Windows to run and might not support .NET Core.</span></span> <span data-ttu-id="83620-116">如果这些软件包对于应用程序至关重要，那么将需要在 Windows 容器上使用 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="83620-116">If those packages are critical for your application, then you will need to use .NET Framework on Windows Containers.</span></span>

## <a name="using-net-technologies-not-available-for-net-core"></a><span data-ttu-id="83620-117">使用不可用于 .NET Core 的 .NET 技术</span><span class="sxs-lookup"><span data-stu-id="83620-117">Using .NET technologies not available for .NET Core</span></span> 

<span data-ttu-id="83620-118">当前版本的 .NET Core（撰写本文时为 2.0 版）中没有提供某些 .NET Framework 技术。</span><span class="sxs-lookup"><span data-stu-id="83620-118">Some .NET Framework technologies are not available in the current version of .NET Core (version 2.0 as of this writing).</span></span> <span data-ttu-id="83620-119">虽然某些技术将在更高版本的 .NET Core (.NET Core 2.x) 中提供，但其他技术不适用于 .NET Core 面向的新应用程序模式，因此可能永远不可用。</span><span class="sxs-lookup"><span data-stu-id="83620-119">Some of them will be available in later .NET Core releases (.NET Core 2.x), but others do not apply to the new application patterns targeted by .NET Core and might never be available.</span></span>

<span data-ttu-id="83620-120">以下列表展示了在 .NET Core 2.0 中不可用的大多数技术：</span><span class="sxs-lookup"><span data-stu-id="83620-120">The following list shows most of the technologies that are not available in .NET Core 2.0:</span></span>

-   <span data-ttu-id="83620-121">ASP.NET Web 窗体。</span><span class="sxs-lookup"><span data-stu-id="83620-121">ASP.NET Web Forms.</span></span> <span data-ttu-id="83620-122">该技术仅在 .NET Framework 上可用。</span><span class="sxs-lookup"><span data-stu-id="83620-122">This technology is only available on .NET Framework.</span></span> <span data-ttu-id="83620-123">目前没有将 ASP.NET Web 窗体引入 .NET Core 的计划。</span><span class="sxs-lookup"><span data-stu-id="83620-123">Currently there are no plans to bring ASP.NET Web Forms to .NET Core.</span></span>

-   <span data-ttu-id="83620-124">WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="83620-124">WCF services.</span></span> <span data-ttu-id="83620-125">即使从 2017 年年中开始，可通过 [WCF 客户端库](https://github.com/dotnet/wcf)从 .NET Core 使用 WCF 服务，</span><span class="sxs-lookup"><span data-stu-id="83620-125">Even when a [WCF-Client library](https://github.com/dotnet/wcf) is available to consume WCF services from .NET Core.</span></span> <span data-ttu-id="83620-126">WCF 服务器实现也只在 .NET Framework 上可用。</span><span class="sxs-lookup"><span data-stu-id="83620-126">as of mid-2017, the WCF server implementation is only available on .NET Framework.</span></span> <span data-ttu-id="83620-127">未来的 .NET Core 版本可能会考虑这种情况。</span><span class="sxs-lookup"><span data-stu-id="83620-127">This scenario might be considered for future releases of .NET Core.</span></span>

-   <span data-ttu-id="83620-128">与工作流相关的服务。</span><span class="sxs-lookup"><span data-stu-id="83620-128">Workflow-related services.</span></span> <span data-ttu-id="83620-129">Windows Workflow Foundation (WF)、工作流服务（WCF + 单个服务中的 WF）和 WCF Data Services（以前称为 ADO.NET Data Services）仅在 .NET Framework 上可用。</span><span class="sxs-lookup"><span data-stu-id="83620-129">Windows Workflow Foundation (WF), Workflow Services (WCF + WF in a single service), and WCF Data Services (formerly known as ADO.NET Data Services) are only available on .NET Framework.</span></span> <span data-ttu-id="83620-130">尚未计划将其引入 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="83620-130">There are currently no plans to bring them to .NET Core.</span></span>

<span data-ttu-id="83620-131">除了官方 [.NET Core 路线图](https://github.com/aspnet/Home/wiki/Roadmap)中列出的技术之外，可能还会将其他功能移植到 .NET Core 中。</span><span class="sxs-lookup"><span data-stu-id="83620-131">In addition to the technologies listed in the official [.NET Core roadmap](https://github.com/aspnet/Home/wiki/Roadmap), other features might be ported to .NET Core.</span></span> <span data-ttu-id="83620-132">有关完整列表，请查看 CoreFX GitHub 站点上标记为 [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) 的项目。</span><span class="sxs-lookup"><span data-stu-id="83620-132">For a full list, look at the items tagged as [port-to-core](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aport-to-core) on the CoreFX GitHub site.</span></span> <span data-ttu-id="83620-133">请注意，此列表不代表 Microsoft 承诺将这些组件引入 .NET Core，而只表示从社区搜集到的一些请求。</span><span class="sxs-lookup"><span data-stu-id="83620-133">Note that this list does not represent a commitment from Microsoft to bring those components to .NET Core — the items simply capture requests from the community.</span></span> <span data-ttu-id="83620-134">如果对以上所列的任何组件感兴趣，请参与 GitHub 上的讨论，发表你的看法。</span><span class="sxs-lookup"><span data-stu-id="83620-134">If you care about any of the components listed above, consider participating in the discussions on GitHub so that your voice can be heard.</span></span> <span data-ttu-id="83620-135">如果认为丢失了某些内容，请[在 CoreFX 存储库中提出新的问题](https://github.com/dotnet/corefx/issues/new)。</span><span class="sxs-lookup"><span data-stu-id="83620-135">And if you think something is missing, please [file a new issue in the CoreFX repository](https://github.com/dotnet/corefx/issues/new).</span></span>

## <a name="using-a-platform-or-api-that-does-not-support-net-core"></a><span data-ttu-id="83620-136">使用不支持 .NET Core 的平台或 API</span><span class="sxs-lookup"><span data-stu-id="83620-136">Using a platform or API that does not support .NET Core</span></span>

<span data-ttu-id="83620-137">某些 Microsoft 或第三方平台不支持 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="83620-137">Some Microsoft or third-party platforms do not support .NET Core.</span></span> <span data-ttu-id="83620-138">例如，某些 Azure 服务提供尚不可用于 .NET Core 的 SDK。</span><span class="sxs-lookup"><span data-stu-id="83620-138">For example, some Azure services provide an SDK that is not yet available for consumption on .NET Core.</span></span> <span data-ttu-id="83620-139">这只是暂时的，因为所有 Azure 服务最终都会使用 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="83620-139">This is temporary, because all Azure services will eventually use .NET Core.</span></span> <span data-ttu-id="83620-140">例如，[Azure DocumentDB SDK for .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) 是在 2016 年 11 月 16 日发布的预览版，但现在已发布正式版 (GA) 作为稳定版本。</span><span class="sxs-lookup"><span data-stu-id="83620-140">For example, the [Azure DocumentDB SDK for .NET Core](https://www.nuget.org/packages/Microsoft.Azure.DocumentDB.Core/1.2.1) was released as a preview on November 16, 2016, but it is now generally available (GA) as a stable version.</span></span>

<span data-ttu-id="83620-141">在此期间，如果 Azure 中的任何平台或服务仍然不支持 .NET Core 及其客户端 API，则可以使用 Azure 服务中的等效 REST API 或 .NET Framework 上的客户端 SDK。</span><span class="sxs-lookup"><span data-stu-id="83620-141">In the meantime, if any platform or service in Azure still doesn’t support .NET Core with its client API, you can use the equivalent REST API from the Azure service or the client SDK on .NET Framework.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="83620-142">其他资源</span><span class="sxs-lookup"><span data-stu-id="83620-142">Additional resources</span></span>

-   <span data-ttu-id="83620-143">**.NET Core 指南**
    [https://docs.microsoft.com/dotnet/core/index](../../../core/index.md)</span><span class="sxs-lookup"><span data-stu-id="83620-143">**.NET Core Guide**
[*https://docs.microsoft.com/dotnet/core/index*](../../../core/index.md)</span></span>

-   <span data-ttu-id="83620-144">**从 .NET Framework 移植到 .NET Core**
    [https://docs.microsoft.com/dotnet/core/porting/index](../../../core/porting/index.md)</span><span class="sxs-lookup"><span data-stu-id="83620-144">**Porting from .NET Framework to .NET Core**
[*https://docs.microsoft.com/dotnet/core/porting/index*](../../../core/porting/index.md)</span></span>

-   <span data-ttu-id="83620-145">**Docker 上的 .NET Framework 指南**
    [https://docs.microsoft.com/dotnet/framework/docker/](../../../framework/docker/index.md)</span><span class="sxs-lookup"><span data-stu-id="83620-145">**.NET Framework on Docker Guide**
[*https://docs.microsoft.com/dotnet/framework/docker/*](../../../framework/docker/index.md)</span></span>

-   <span data-ttu-id="83620-146">**.NET 组件概述**
    [https://docs.microsoft.com/dotnet/standard/components](../../components.md)</span><span class="sxs-lookup"><span data-stu-id="83620-146">**.NET Components Overview**
[*https://docs.microsoft.com/dotnet/standard/components*](../../components.md)</span></span>




>[!div class="step-by-step"]
<span data-ttu-id="83620-147">[上一篇] (net-core-container-scenarios.md) [下一篇] (container-framework-choice-factors.md)</span><span class="sxs-lookup"><span data-stu-id="83620-147">[Previous] (net-core-container-scenarios.md) [Next] (container-framework-choice-factors.md)</span></span>
