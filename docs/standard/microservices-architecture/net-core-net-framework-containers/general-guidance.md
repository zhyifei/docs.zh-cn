---
title: "通用指南"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 通用指南"
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
ms.openlocfilehash: fa58d1d81b2d1523baf123d4963db2ca00fee15d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="general-guidance"></a><span data-ttu-id="66a64-104">通用指南</span><span class="sxs-lookup"><span data-stu-id="66a64-104">General guidance</span></span>

<span data-ttu-id="66a64-105">本部分提供有关何时选择 .NET Core 或 .NET Framework 的总结。</span><span class="sxs-lookup"><span data-stu-id="66a64-105">This section provides a summary of when to choose .NET Core or .NET Framework.</span></span> <span data-ttu-id="66a64-106">后面各部分将提供对上述选择的详细介绍。</span><span class="sxs-lookup"><span data-stu-id="66a64-106">We provide more details about these choices in the sections that follow.</span></span>

<span data-ttu-id="66a64-107">将 .NET Core 与 Linux 或 Windows 容器结合使用并用于容器化 Docker 服务器应用程序的适用情况：</span><span class="sxs-lookup"><span data-stu-id="66a64-107">You should use .NET Core, with Linux or Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="66a64-108">用户有跨平台需求。</span><span class="sxs-lookup"><span data-stu-id="66a64-108">You have cross-platform needs.</span></span> <span data-ttu-id="66a64-109">例如，想同时使用 Linux 和 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="66a64-109">For example, you want to use both Linux and Windows Containers.</span></span>

-   <span data-ttu-id="66a64-110">应用程序体系结构基于微服务。</span><span class="sxs-lookup"><span data-stu-id="66a64-110">Your application architecture is based on microservices.</span></span>

-   <span data-ttu-id="66a64-111">需快速启动容器且每个容器内存占用较小，以实现更好的密度，或每个硬件单位中的容器较多，以降低成本。</span><span class="sxs-lookup"><span data-stu-id="66a64-111">You need to start containers fast and want a small footprint per container to achieve better density or more containers per hardware unit in order to lower your costs.</span></span>

<span data-ttu-id="66a64-112">简单地说，在创建新的容器化 .NET 应用程序时，应考虑将 .NET Core 作为默认选择。</span><span class="sxs-lookup"><span data-stu-id="66a64-112">In short, when you create new containerized .NET applications, you should consider .NET Core as the default choice.</span></span> <span data-ttu-id="66a64-113">它具有许多好处，并最匹配容器的基本原理和运行方式。</span><span class="sxs-lookup"><span data-stu-id="66a64-113">It has many benefits and fits best with the containers philosophy and style of working.</span></span>

<span data-ttu-id="66a64-114">使用 .NET Core 的另一个好处是可在同一台计算机中并行运行 .NET 版本的应用程序。</span><span class="sxs-lookup"><span data-stu-id="66a64-114">An additional benefit of using .NET Core is that you can run side by side .NET versions for applications within the same machine.</span></span> <span data-ttu-id="66a64-115">这一优势对于不使用容器的服务器或虚拟机而言更为重要，因为容器会隔离应用所需的 .NET 版本。</span><span class="sxs-lookup"><span data-stu-id="66a64-115">This benefit is more important for servers or VMs that do not use containers, because containers isolate the versions of .NET that the app needs.</span></span> <span data-ttu-id="66a64-116">（只要它们与基础操作系统兼容。）</span><span class="sxs-lookup"><span data-stu-id="66a64-116">(As long as they are compatible with the underlying OS.)</span></span>

<span data-ttu-id="66a64-117">将 .NET Framework 与 Windows 容器结合使用并用于容器化 Docker 服务器应用程序的适用情况：</span><span class="sxs-lookup"><span data-stu-id="66a64-117">You should use .NET Framework, with Windows Containers, for your containerized Docker server application when:</span></span>

-   <span data-ttu-id="66a64-118">应用程序当前使用 .NET Framework 并在 Windows 上具有强依赖关系。</span><span class="sxs-lookup"><span data-stu-id="66a64-118">Your application currently uses .NET Framework and has strong dependencies on Windows.</span></span>

-   <span data-ttu-id="66a64-119">需要使用 .NET Core 不支持的 Windows API。</span><span class="sxs-lookup"><span data-stu-id="66a64-119">You need to use Windows APIs that are not supported by .NET Core.</span></span>

-   <span data-ttu-id="66a64-120">用户需要使用不可用于 .NET Core 的第三方 .NET 库或 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="66a64-120">You need to use third-party .NET libraries or NuGet packages that are not available for .NET Core.</span></span>

<span data-ttu-id="66a64-121">在 Docker 上使用.NET Framework 可通过最大限度地减少部署问题来提升部署体验。</span><span class="sxs-lookup"><span data-stu-id="66a64-121">Using .NET Framework on Docker can improve your deployment experiences by minimizing deployment issues.</span></span> <span data-ttu-id="66a64-122">此[*“提升和移动”方案*](https://aka.ms/liftandshiftwithcontainersebook)对于针对最初使用传统 .NET Framework（如 ASP.NET WebForms、MVC web 应用或 WCF (Windows Communication Foundation) 服务）开发的旧应用程序实施容器化而言很重要。</span><span class="sxs-lookup"><span data-stu-id="66a64-122">This [*"lift and shift" scenario*](https://aka.ms/liftandshiftwithcontainersebook) is important for containerizing legacy applications that were originally developed with the traditional .NET Framework, like ASP.NET WebForms, MVC web apps or WCF (Windows Communication Foundation) services.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="66a64-123">其他资源</span><span class="sxs-lookup"><span data-stu-id="66a64-123">Additional resources</span></span>

-   <span data-ttu-id="66a64-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**（电子书：使用 Azure 和 Windows 容器更新现有 .NET Framework 应用程序）
    [https://aka.ms/liftandshiftwithcontainersebook](https://aka.ms/liftandshiftwithcontainersebook)</span><span class="sxs-lookup"><span data-stu-id="66a64-124">**e-book: Modernize existing .NET Framework applications with Azure and Windows Containers**
[*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)</span></span>

-   <span data-ttu-id="66a64-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**（示例应用：使用 Windows 容器更新旧的 ASP.NET web 应用）
    [https://aka.ms/eshopmodernizing](https://aka.ms/eshopmodernizing)</span><span class="sxs-lookup"><span data-stu-id="66a64-125">**Sample apps: Modernization of legacy ASP.NET web apps by using Windows Containers**
[*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="66a64-126">[上一项] (index.md) [下一项] (net-core-container-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="66a64-126">[Previous] (index.md) [Next] (net-core-container-scenarios.md)</span></span>
