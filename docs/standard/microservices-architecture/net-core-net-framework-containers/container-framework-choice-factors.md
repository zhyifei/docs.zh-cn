---
title: 决策表。 用于 Docker 的 .NET Framework
description: 适用于容器化 .NET 应用程序的 .NET 微服务体系结构 | 决策表，用于 Docker 的 .NET Framework
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: 0e384fabca88d8ad6f93ae626140fb3d5dcaf971
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589316"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="d1bba-104">决策表：用于 Docker 的 .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1bba-104">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="d1bba-105">下面汇总了是使用 .NET Framework 还是 .NET Core、Windows 还是 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-105">The following summarizes whether to use .NET Framework or .NET Core, and Windows or Linux containers.</span></span> <span data-ttu-id="d1bba-106">请记住，对于 Linux 容器，你需要基于 Linux 的 Docker 主机（VM 或服务器）；对于 Windows 容器，你需要基于 Windows Server 的 Docker 主机（VM 或服务器）。</span><span class="sxs-lookup"><span data-stu-id="d1bba-106">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

<span data-ttu-id="d1bba-107">有几个应用程序的功能会影响你的决定。</span><span class="sxs-lookup"><span data-stu-id="d1bba-107">There are several features of your application that affect your decision.</span></span> <span data-ttu-id="d1bba-108">作决定时，应权衡这些功能的重要性。</span><span class="sxs-lookup"><span data-stu-id="d1bba-108">You should weigh the importance of these features when making your decision.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1bba-109">开发计算机将运行一个 Docker 主机，Linux 或 Windows 均可。</span><span class="sxs-lookup"><span data-stu-id="d1bba-109">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="d1bba-110">想在一个解决方案中一起运行和测试的相关微服务都需要在同一容器平台上运行。</span><span class="sxs-lookup"><span data-stu-id="d1bba-110">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

* <span data-ttu-id="d1bba-111">应用程序体系结构要选择容器上的微服务。</span><span class="sxs-lookup"><span data-stu-id="d1bba-111">Your application architecture choice is **Microservices on containers**.</span></span>
    - <span data-ttu-id="d1bba-112">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d1bba-112">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d1bba-113">容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-113">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="d1bba-114">应用程序体系结构要选择整体式应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1bba-114">Your application architecture choice is a **Monolithic application**.</span></span>
    - <span data-ttu-id="d1bba-115">.NET 实现可以选择 .NET Core 或 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="d1bba-115">Your .NET implementation choice can be either *.NET Core* or *.NET Framework*.</span></span>
    - <span data-ttu-id="d1bba-116">如果选择 .NET Core，容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-116">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="d1bba-117">如果选择的是 .NET Framework，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-117">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="d1bba-118">应用程序是基于容器的新开发（“绿色字段”）。</span><span class="sxs-lookup"><span data-stu-id="d1bba-118">Your application is a  **New container-based development ("green-field")**.</span></span>
    - <span data-ttu-id="d1bba-119">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d1bba-119">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d1bba-120">容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-120">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="d1bba-121">应用程序是到容器的 Windows Server 旧应用程序（“棕色字段”）迁移</span><span class="sxs-lookup"><span data-stu-id="d1bba-121">Your application is a **Windows Server legacy app ("brown-field") migration to containers**</span></span>
    - <span data-ttu-id="d1bba-122">.NET 实现要选择基于框架依赖关系的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="d1bba-122">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="d1bba-123">因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-123">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="d1bba-124">应用程序的设计目标是同类最佳的性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="d1bba-124">Your application's design goal is **Best-in-class performance and scalability**.</span></span>
    - <span data-ttu-id="d1bba-125">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d1bba-125">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d1bba-126">容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-126">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="d1bba-127">使用 ASP.NET Core 生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1bba-127">You built your application using **ASP.NET Core**.</span></span>
    - <span data-ttu-id="d1bba-128">.NET 实现应选择 .NET Core。</span><span class="sxs-lookup"><span data-stu-id="d1bba-128">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="d1bba-129">如果有其他框架依赖关系，可以使用 .NET Framework 实现。</span><span class="sxs-lookup"><span data-stu-id="d1bba-129">You can use the *.NET Framework* implementation, if you have other framework dependencies.</span></span>
    - <span data-ttu-id="d1bba-130">如果选择 .NET Core，容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-130">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="d1bba-131">如果选择的是 .NET Framework，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-131">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="d1bba-132">使用 ASP.NET 4（MVC 5、Web API 2 和 Web Forms）生成了应用程序。</span><span class="sxs-lookup"><span data-stu-id="d1bba-132">You built your application using **ASP.NET 4 (MVC 5, Web API 2, and Web Forms)**.</span></span>
    - <span data-ttu-id="d1bba-133">.NET 实现要选择基于框架依赖关系的 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="d1bba-133">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="d1bba-134">因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-134">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="d1bba-135">应用程序使用 SignalR 服务。</span><span class="sxs-lookup"><span data-stu-id="d1bba-135">Your application uses **SignalR services**.</span></span>
    - <span data-ttu-id="d1bba-136">.NET 实现可以选择 .NET Framework 或者 .NET Core 2.1（如发布）或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d1bba-136">Your .NET implementation choice can be *.NET Framework*, or *.NET Core 2.1 (when released) or later*.</span></span>
    - <span data-ttu-id="d1bba-137">如果选择 .NET Framework 中的 SignalR 实现，则容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-137">Your container platform choice must be *Windows containers* if you chose the SignalR implementation in .NET Framework.</span></span>
    - <span data-ttu-id="d1bba-138">如果选择 .NET Core 2.1 或更高版本（如发布）中的 SignalR 实现，则容器平台可以选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-138">Your container platform choice can be either Linux containers or Windows containers if you chose the SignalR implementation in .NET Core 2.1 or later (when released).</span></span>  
    - <span data-ttu-id="d1bba-139">当 SignalR 服务在 .NET Core 上运行时，可以使用 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-139">When **SignalR services** run on *.NET Core*, you can use *Linux containers or Windows Containers*.</span></span>
* <span data-ttu-id="d1bba-140">应用程序使用 WCF、WF 和其他旧框架。</span><span class="sxs-lookup"><span data-stu-id="d1bba-140">Your application uses **WCF, WF, and other legacy frameworks**.</span></span>
    - <span data-ttu-id="d1bba-141">.NET 实现可以选择 .NET Framework 或 .NET Core（未来版本的路线图中）。</span><span class="sxs-lookup"><span data-stu-id="d1bba-141">Your .NET implementation choice is *.NET Framework*, or *.NET Core (in the roadmap for a future release)*.</span></span>
    - <span data-ttu-id="d1bba-142">因为 .NET Framework 依赖关系，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-142">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="d1bba-143">应用程序涉及 Azure 服务的消耗。</span><span class="sxs-lookup"><span data-stu-id="d1bba-143">Your application involves **Consumption of Azure services**.</span></span>
    - <span data-ttu-id="d1bba-144">.NET 实现可以选择 .NET Framework 或 .NET Core（最终所有 Azure 服务都将为 .NET Core 提供客户端 SDK）。</span><span class="sxs-lookup"><span data-stu-id="d1bba-144">Your .NET implementation choice is *.NET Framework*, or *.NET Core (eventually all Azure services will provide client SDKs for .NET Core)*.</span></span>
    - <span data-ttu-id="d1bba-145">如果使用 .NET Framework 客户端 API，容器平台必须选择 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-145">Your container platform choice must be *Windows containers* if you use .NET Framework client APIs.</span></span>
    - <span data-ttu-id="d1bba-146">如果使用适用于 .NET Core 的客户端 API，还可选择 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="d1bba-146">If you use client APIs available for *.NET Core*, you can also choose between *Linux containers and Windows containers*.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="d1bba-147">[上一页] (net-framework-container-scenarios.md) [下一页] (net-container-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="d1bba-147">[Previous] (net-framework-container-scenarios.md) [Next] (net-container-os-targets.md)</span></span>
