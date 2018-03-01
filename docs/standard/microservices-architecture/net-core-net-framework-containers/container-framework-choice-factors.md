---
title: "决策表。 用于 Docker 的 .NET Framework"
description: "适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 决策表，用于 Docker 的 .NET Framework"
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
ms.openlocfilehash: 40e6a14e7e3515194185e1f4558c91ac29429108
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="d66e0-105">决策表：用于 Docker 的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d66e0-105">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="d66e0-106">下面汇总了是使用 .NET Framework 还是 .NET Core、Windows 还是 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-106">The following summarizes whether to use .NET Framework or .NET Core, and Windows or Linux containers.</span></span> <span data-ttu-id="d66e0-107">请记住，对于 Linux 容器，你需要基于 Linux 的 Docker 主机（VM 或服务器）；对于 Windows 容器，你需要基于 Windows Server 的 Docker 主机（VM 或服务器）。</span><span class="sxs-lookup"><span data-stu-id="d66e0-107">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

<span data-ttu-id="d66e0-108">有几个应用程序的功能会影响你的决定。</span><span class="sxs-lookup"><span data-stu-id="d66e0-108">There are several features of your application that affect your decision.</span></span> <span data-ttu-id="d66e0-109">作决定时，应权衡这些功能的重要性。</span><span class="sxs-lookup"><span data-stu-id="d66e0-109">You should weigh the importance of these features when making your decision.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d66e0-110">开发计算机将运行一个 Docker 主机，Linux 或 Windows 均可。</span><span class="sxs-lookup"><span data-stu-id="d66e0-110">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="d66e0-111">想在一个解决方案中一起运行和测试的相关微服务都需要在同一容器平台上运行。</span><span class="sxs-lookup"><span data-stu-id="d66e0-111">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

* <span data-ttu-id="d66e0-112">应用程序体系结构要选择容器上的微服务。</span><span class="sxs-lookup"><span data-stu-id="d66e0-112">Your application architecture choice is **Microservices on containers**.</span></span>
    - <span data-ttu-id="d66e0-113">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d66e0-113">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d66e0-114">容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-114">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="d66e0-115">应用程序体系结构要选择整体式应用程序。</span><span class="sxs-lookup"><span data-stu-id="d66e0-115">Your application architecture choice is a **Monolithic application**.</span></span>
    - <span data-ttu-id="d66e0-116">.NET 实现可以选择 .NET Core 或 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="d66e0-116">Your .NET implementation choice can be either *.NET Core* or *.NET Framework*.</span></span>
    - <span data-ttu-id="d66e0-117">如果选择 .NET Core，容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-117">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="d66e0-118">如果选择的是 .NET Framework，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-118">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="d66e0-119">应用程序是基于容器的新开发（“绿色字段”）。</span><span class="sxs-lookup"><span data-stu-id="d66e0-119">Your application is a  **New container-based development ("green-field")**.</span></span>
    - <span data-ttu-id="d66e0-120">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d66e0-120">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d66e0-121">容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-121">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="d66e0-122">应用程序是到容器的 Windows Server 旧应用程序（“棕色字段”）迁移</span><span class="sxs-lookup"><span data-stu-id="d66e0-122">Your application is a **Windows Server legacy app ("brown-field") migration to containers**</span></span>
    - <span data-ttu-id="d66e0-123">.NET 实现要选择基于框架依赖关系的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="d66e0-123">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="d66e0-124">因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-124">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="d66e0-125">应用程序的设计目标是同类最佳的性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="d66e0-125">Your application's design goal is **Best-in-class performance and scalability**.</span></span>
    - <span data-ttu-id="d66e0-126">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d66e0-126">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d66e0-127">容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-127">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="d66e0-128">使用 ASP.NET Core 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="d66e0-128">You built your application using **ASP.NET Core**.</span></span>
    - <span data-ttu-id="d66e0-129">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d66e0-129">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d66e0-130">如果有其他框架依赖关系，可以使用 .NET Framework 实现。</span><span class="sxs-lookup"><span data-stu-id="d66e0-130">You can use the *.NET Framework* implementation, if you have other framework dependencies.</span></span>
    - <span data-ttu-id="d66e0-131">如果选择 .NET Core，容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-131">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="d66e0-132">如果选择的是 .NET Framework，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-132">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="d66e0-133">使用 ASP.NET 4（MVC 5、Web API 2 和 Web Forms）生成了应用程序。</span><span class="sxs-lookup"><span data-stu-id="d66e0-133">You built your application using **ASP.NET 4 (MVC 5, Web API 2, and Web Forms)**.</span></span>
    - <span data-ttu-id="d66e0-134">.NET 实现要选择基于框架依赖关系的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="d66e0-134">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="d66e0-135">因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-135">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="d66e0-136">应用程序使用 SignalR 服务。</span><span class="sxs-lookup"><span data-stu-id="d66e0-136">Your application uses **SignalR services**.</span></span>
    - <span data-ttu-id="d66e0-137">.NET 实现可以选择 .NET Framework 或者 .NET Core 2.1（如发布）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d66e0-137">Your .NET implementation choice can be *.NET Framework*, or *.NET Core 2.1 (when released) or later*.</span></span>
    - <span data-ttu-id="d66e0-138">如果选择 .NET Framework 中的 SignalR 实现，则容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-138">Your container platform choice must be *Windows containers* if you chose the SignalR implementation in .NET Framework.</span></span>
    - <span data-ttu-id="d66e0-139">如果选择 .NET Core 2.1 或更高版本（如发布）中的 SignalR 实现，则容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-139">Your container platform choice can be either Linux containers or Windows containers if you chose the SignalR implementation in .NET Core 2.1 or later (when released).</span></span>  
    - <span data-ttu-id="d66e0-140">当 SignalR 服务在 .NET Core 上运行时，可以使用 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-140">When **SignalR services** run on *.NET Core*, you can use *Linux containers or Windows Containers*.</span></span>
* <span data-ttu-id="d66e0-141">应用程序使用 WCF、WF 和其他旧框架。</span><span class="sxs-lookup"><span data-stu-id="d66e0-141">Your application uses **WCF, WF, and other legacy frameworks**.</span></span>
    - <span data-ttu-id="d66e0-142">.NET 实现可以选择 .NET Framework 或 .NET Core（未来版本的路线图中）。</span><span class="sxs-lookup"><span data-stu-id="d66e0-142">Your .NET implementation choice is *.NET Framework*, or *.NET Core (in the roadmap for a future release)*.</span></span>
    - <span data-ttu-id="d66e0-143">因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-143">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="d66e0-144">应用程序涉及 Azure 服务的消耗。</span><span class="sxs-lookup"><span data-stu-id="d66e0-144">Your application involves **Consumption of Azure services**.</span></span>
    - <span data-ttu-id="d66e0-145">.NET 实现可以选择 .NET Framework 或 .NET Core（最终所有 Azure 服务都将为 .NET Core 提供客户端 SDK）。</span><span class="sxs-lookup"><span data-stu-id="d66e0-145">Your .NET implementation choice is *.NET Framework*, or *.NET Core (eventually all Azure services will provide client SDKs for .NET Core)*.</span></span>
    - <span data-ttu-id="d66e0-146">如果使用 .NET Framework 客户端 API，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-146">Your container platform choice must be *Windows containers* if you use .NET Framework client APIs.</span></span>
    - <span data-ttu-id="d66e0-147">如果使用适用于 .NET Core 的客户端 API，还可选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d66e0-147">If you use client APIs available for *.NET Core*, you can also choose between *Linux containers and Windows containers*.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d66e0-148">[上一页] (net-framework-container-scenarios.md) [下一页] (net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="d66e0-148">[Previous] (net-framework-container-scenarios.md) [Next] (net-container-os-targets.md)</span></span>
