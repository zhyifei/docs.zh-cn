---
title: "决策表。 .NET 框架，用于 Docker"
description: "为容器化的.NET 应用程序的.NET 微服务体系结构 |决策表，.NET 框架，用于 Docker"
keywords: "Docker, 微服务, ASP.NET, 容器"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4889662c4d887bebd320389e3ced6aae1c93133b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a><span data-ttu-id="bc55f-105">决策表：.NET 框架，用于 Docker</span><span class="sxs-lookup"><span data-stu-id="bc55f-105">Decision table: .NET frameworks to use for Docker</span></span>

<span data-ttu-id="bc55f-106">下面汇总了是否使用.NET Framework 或.NET Core 和 Windows 或 Linux 容器。</span><span class="sxs-lookup"><span data-stu-id="bc55f-106">The following summarizes whether to use .NET Framework or .NET Core, and Windows or Linux containers.</span></span> <span data-ttu-id="bc55f-107">请记住，对于 Linux 容器，你需要基于 Linux 的 Docker 主机 （Vm 或服务器） 和为 Windows 容器需要 Windows Server 基于 Docker 主机 （Vm 或服务器）。</span><span class="sxs-lookup"><span data-stu-id="bc55f-107">Remember that for Linux containers, you need Linux-based Docker hosts (VMs or servers) and that for Windows Containers you need Windows Server based Docker hosts (VMs or servers).</span></span>

<span data-ttu-id="bc55f-108">有几个应用程序的功能，它们会影响你的决策。</span><span class="sxs-lookup"><span data-stu-id="bc55f-108">There are several features of your application that affect your decision.</span></span> <span data-ttu-id="bc55f-109">做这些决定时，你应权衡这些功能的重要性。</span><span class="sxs-lookup"><span data-stu-id="bc55f-109">You should weigh the importance of these features when making your decision.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bc55f-110">开发计算机将运行一个 Docker 主机，Linux 或 Windows。</span><span class="sxs-lookup"><span data-stu-id="bc55f-110">Your development machines will run one Docker host, either Linux or Windows.</span></span> <span data-ttu-id="bc55f-111">你想要运行和测试在一起在一个解决方案中的相关微服务将所有需要的相同容器平台上运行。</span><span class="sxs-lookup"><span data-stu-id="bc55f-111">Related microservices that you want to run and test together in one solution will all need to run on the same container platform.</span></span>

* <span data-ttu-id="bc55f-112">您的应用程序体系结构选择**在容器上的微服务**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-112">Your application architecture choice is **Microservices on containers**.</span></span>
    - <span data-ttu-id="bc55f-113">应为.NET 实现自选*.NET 核心*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-113">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="bc55f-114">平台自选容器可以是*Linux 容器*或*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-114">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="bc55f-115">您的应用程序体系结构选择**整体应用程序**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-115">Your application architecture choice is a **Monolithic application**.</span></span>
    - <span data-ttu-id="bc55f-116">.NET 实现自选可以是*.NET 核心*或*.NET Framework*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-116">Your .NET implementation choice can be either *.NET Core* or *.NET Framework*.</span></span>
    - <span data-ttu-id="bc55f-117">如果你已选择*.NET 核心*，自选容器平台可以是*Linux 容器*或*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-117">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="bc55f-118">如果你已选择*.NET Framework*，你的容器平台选择必须用*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-118">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="bc55f-119">你的应用程序**新容器基于开发 （"绿色的字段"）**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-119">Your application is a  **New container-based development ("green-field")**.</span></span>
    - <span data-ttu-id="bc55f-120">应为.NET 实现自选*.NET 核心*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-120">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="bc55f-121">平台自选容器可以是*Linux 容器*或*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-121">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="bc55f-122">你的应用程序**Windows Server 旧应用程序 （"部分的字段"） 迁移到容器**</span><span class="sxs-lookup"><span data-stu-id="bc55f-122">Your application is a **Windows Server legacy app ("brown-field") migration to containers**</span></span>
    - <span data-ttu-id="bc55f-123">.NET 实现自选是*.NET Framework*基于框架依赖项。</span><span class="sxs-lookup"><span data-stu-id="bc55f-123">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="bc55f-124">你的容器平台选择必须用*Windows 容器*由于.NET Framework 依赖性。</span><span class="sxs-lookup"><span data-stu-id="bc55f-124">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="bc55f-125">应用程序的设计目标是**同类最佳性能和可伸缩性**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-125">Your application's design goal is **Best-in-class performance and scalability**.</span></span>
    - <span data-ttu-id="bc55f-126">应为.NET 实现自选*.NET 核心*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-126">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="bc55f-127">平台自选容器可以是*Linux 容器*或*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-127">Your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
* <span data-ttu-id="bc55f-128">你应用程序使用生成**ASP.NET Core**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-128">You built your application using **ASP.NET Core**.</span></span>
    - <span data-ttu-id="bc55f-129">应为.NET 实现自选*.NET 核心*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-129">Your .NET implementation choice should be *.NET Core*.</span></span>
    - <span data-ttu-id="bc55f-130">你可以使用*.NET Framework*实现中，如果你有其他框架依赖项。</span><span class="sxs-lookup"><span data-stu-id="bc55f-130">You can use the *.NET Framework* implementation, if you have other framework dependencies.</span></span>
    - <span data-ttu-id="bc55f-131">如果你已选择*.NET 核心*，自选容器平台可以是*Linux 容器*或*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-131">If you have chosen *.NET Core*, your container platform choice can be either *Linux containers* or *Windows containers*.</span></span>
    - <span data-ttu-id="bc55f-132">如果你已选择*.NET Framework*，你的容器平台选择必须用*Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-132">If you have chosen *.NET Framework*, your container platform choice must be *Windows containers*.</span></span>
* <span data-ttu-id="bc55f-133">你应用程序使用生成**ASP.NET 4 （MVC 5，Web API 2 和 Web 窗体）**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-133">You built your application using **ASP.NET 4 (MVC 5, Web API 2, and Web Forms)**.</span></span>
    - <span data-ttu-id="bc55f-134">.NET 实现自选是*.NET Framework*基于框架依赖项。</span><span class="sxs-lookup"><span data-stu-id="bc55f-134">Your .NET implementation choice is *.NET Framework* based on framework dependency.</span></span>
    - <span data-ttu-id="bc55f-135">你的容器平台选择必须用*Windows 容器*由于.NET Framework 依赖性。</span><span class="sxs-lookup"><span data-stu-id="bc55f-135">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="bc55f-136">你的应用程序使用**SignalR 服务**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-136">Your application uses **SignalR services**.</span></span>
    - <span data-ttu-id="bc55f-137">你的.NET 实现选择可以用*.NET Framework*，或*.NET 核心 2.1 （如果已发布） 或更高版本*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-137">Your .NET implementation choice can be *.NET Framework*, or *.NET Core 2.1 (when released) or later*.</span></span>
    - <span data-ttu-id="bc55f-138">你的容器平台选择必须用*Windows 容器*如果.NET Framework 中选择的 SignalR 实现。</span><span class="sxs-lookup"><span data-stu-id="bc55f-138">Your container platform choice must be *Windows containers* if you chose the SignalR implementation in .NET Framework.</span></span>
    - <span data-ttu-id="bc55f-139">如果你选择的 SignalR 实现在.NET 核心 2.1 或更高版本 （如果已发布），平台自选容器可以是 Linux 容器或 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="bc55f-139">Your container platform choice can be either Linux containers or Windows containers if you chose the SignalR implementation in .NET Core 2.1 or later (when released).</span></span>  
    - <span data-ttu-id="bc55f-140">当**SignalR 服务**上运行*.NET 核心*，你可以使用*Linux 容器或 Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-140">When **SignalR services** run on *.NET Core*, you can use *Linux containers or Windows Containers*.</span></span>
* <span data-ttu-id="bc55f-141">你的应用程序使用**WCF、 WF、 和其他旧框架**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-141">Your application uses **WCF, WF, and other legacy frameworks**.</span></span>
    - <span data-ttu-id="bc55f-142">.NET 实现自选是*.NET Framework*，或*（路线图中拥有将来的版本） 的.NET 核心*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-142">Your .NET implementation choice is *.NET Framework*, or *.NET Core (in the roadmap for a future release)*.</span></span>
    - <span data-ttu-id="bc55f-143">你的容器平台选择必须用*Windows 容器*由于.NET Framework 依赖性。</span><span class="sxs-lookup"><span data-stu-id="bc55f-143">Your container platform choice must be *Windows containers* because of the .NET Framework dependency.</span></span>
* <span data-ttu-id="bc55f-144">应用程序涉及**消耗的 Azure 服务**。</span><span class="sxs-lookup"><span data-stu-id="bc55f-144">Your application involves **Consumption of Azure services**.</span></span>
    - <span data-ttu-id="bc55f-145">.NET 实现自选是*.NET Framework*，或*（最终所有 Azure 服务将为.NET 核心提供客户端 Sdk） 的.NET 核心*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-145">Your .NET implementation choice is *.NET Framework*, or *.NET Core (eventually all Azure services will provide client SDKs for .NET Core)*.</span></span>
    - <span data-ttu-id="bc55f-146">你的容器平台选择必须用*Windows 容器*如果你使用.NET Framework 客户端 Api。</span><span class="sxs-lookup"><span data-stu-id="bc55f-146">Your container platform choice must be *Windows containers* if you use .NET Framework client APIs.</span></span>
    - <span data-ttu-id="bc55f-147">如果你使用客户端 Api 可用于*.NET 核心*，你还可以选择之间*Linux 容器和 Windows 容器*。</span><span class="sxs-lookup"><span data-stu-id="bc55f-147">If you use client APIs available for *.NET Core*, you can also choose between *Linux containers and Windows containers*.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="bc55f-148">[以前](net-framework 的容器-scenarios.md) [下一步] (net-容器-os-targets.md)</span><span class="sxs-lookup"><span data-stu-id="bc55f-148">[Previous] (net-framework-container-scenarios.md) [Next] (net-container-os-targets.md)</span></span>
