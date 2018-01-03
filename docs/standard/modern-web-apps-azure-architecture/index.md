---
title: "使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序"
description: "使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序 | 简介"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 44864274a86634c0199885b5507124f2f54ce0f6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a><span data-ttu-id="1228c-103">使用 ASP.NET Core 和 Azure 构建新式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1228c-103">Architect Modern Web Applications with ASP.NET Core and Azure</span></span>

<span data-ttu-id="1228c-104">相比传统 .NET 开发，.NET Core 和 ASP.NET Core 具有一系列优势。</span><span class="sxs-lookup"><span data-stu-id="1228c-104">.NET Core and ASP.NET Core offer several advantages over traditional .NET development.</span></span> <span data-ttu-id="1228c-105">如果以下所有方面或一些方面对于你的应用程序成功至关重要，应将 .NET Core 用于服务器应用程序：</span><span class="sxs-lookup"><span data-stu-id="1228c-105">You should use .NET Core for your server applications if some or all of the following are important to your application's success:</span></span>

-   <span data-ttu-id="1228c-106">跨平台支持</span><span class="sxs-lookup"><span data-stu-id="1228c-106">Cross-platform support</span></span>

-   <span data-ttu-id="1228c-107">微服务的使用</span><span class="sxs-lookup"><span data-stu-id="1228c-107">Use of microservices</span></span>

-   <span data-ttu-id="1228c-108">Docker 容器的使用</span><span class="sxs-lookup"><span data-stu-id="1228c-108">Use of Docker containers</span></span>

-   <span data-ttu-id="1228c-109">高性能和可伸缩性要求</span><span class="sxs-lookup"><span data-stu-id="1228c-109">High performance and scalability requirements</span></span>

-   <span data-ttu-id="1228c-110">在同一服务器上通过应用程序对 .NET 版本进行并行版本控制</span><span class="sxs-lookup"><span data-stu-id="1228c-110">Side-by-side versioning of .NET versions by application on the same server</span></span>

<span data-ttu-id="1228c-111">传统 .NET 应用程序虽然支持以上要求，但是 ASP.NET Core 和 .NET Core 已经过优化，可为以上方案提供完善的支持。</span><span class="sxs-lookup"><span data-stu-id="1228c-111">Traditional .NET applications can and do support these requirements, but ASP.NET Core and .NET Core have been optimized to offer improved support for the above scenarios.</span></span>

<span data-ttu-id="1228c-112">越来越多的组织选择使用 Microsoft Azure 等服务，在云中托管 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1228c-112">More and more organizations are choosing to host their web applications in the cloud using services like Microsoft Azure.</span></span> <span data-ttu-id="1228c-113">如果以下方面对你的应用程序或组织至关重要，应该考虑在云中托管应用程序：</span><span class="sxs-lookup"><span data-stu-id="1228c-113">You should consider hosting your application in the cloud if the following are important to your application or organization:</span></span>

-   <span data-ttu-id="1228c-114">减少对数据中心的成本投入（硬件、软件、空间、实用工具等）</span><span class="sxs-lookup"><span data-stu-id="1228c-114">Reduced investment in data center costs (hardware, software, space, utilities, etc)</span></span>

-   <span data-ttu-id="1228c-115">灵活的定价（基于使用情况付费，无需为空闲容量付费）</span><span class="sxs-lookup"><span data-stu-id="1228c-115">Flexible pricing (pay based on usage, not for idle capacity)</span></span>

-   <span data-ttu-id="1228c-116">高可靠性</span><span class="sxs-lookup"><span data-stu-id="1228c-116">Extreme reliability</span></span>

-   <span data-ttu-id="1228c-117">改善应用移动性；可轻松更改部署应用的位置和方式</span><span class="sxs-lookup"><span data-stu-id="1228c-117">Improved app mobility; easily change where and how your app is deployed</span></span>

-   <span data-ttu-id="1228c-118">灵活的容量；基于实际需要增加或减少</span><span class="sxs-lookup"><span data-stu-id="1228c-118">Flexible capacity; scale up or down based on actual needs</span></span>

<span data-ttu-id="1228c-119">使用 Microsoft Azure 中托管的 ASP.NET Core 生成 web 应用程序，与传统替代方法相比，这能提供许多竞争优势。</span><span class="sxs-lookup"><span data-stu-id="1228c-119">Building web applications with ASP.NET Core, hosted in Microsoft Azure, offers numerous competitive advantages over traditional alternatives.</span></span> <span data-ttu-id="1228c-120">ASP.NET Core 针对新式 web 应用程序开发做法和云托管方案进行了优化。</span><span class="sxs-lookup"><span data-stu-id="1228c-120">ASP.NET Core is optimized for modern web application development practices and cloud hosting scenarios.</span></span> <span data-ttu-id="1228c-121">本指南介绍如何构建 ASP.NET Core 应用程序，充分利用这些功能。</span><span class="sxs-lookup"><span data-stu-id="1228c-121">In this guide, you will learn how to architect your ASP.NET Core applications to best take advantage of these capabilities.</span></span>

## <a name="purpose"></a><span data-ttu-id="1228c-122">目标</span><span class="sxs-lookup"><span data-stu-id="1228c-122">Purpose</span></span>

<span data-ttu-id="1228c-123">本指南提供了使用 ASP.NET Core 和 Azure 构建单片 web 应用程序的端到端指导。</span><span class="sxs-lookup"><span data-stu-id="1228c-123">This guide provides end-to-end guidance on building monolithic web applications using ASP.NET Core and Azure.</span></span>

<span data-ttu-id="1228c-124">本指南是对“使用 .NET 构建和开发容器化和基于微服务的应用程序”的补充，偏重于 Docker、微服务和托管企业应用程序的容器部署。</span><span class="sxs-lookup"><span data-stu-id="1228c-124">This guide is complementary to the "*Architecting and Developing Containerized and Microservice-based Applications with .NET*" which focuses more on Docker, Microservices, and Deployment of Containers to host enterprise applications.</span></span>

> ### <a name="architecting-and-developing-containerized-microservice-based-apps-in-net"></a><span data-ttu-id="1228c-125">在 .NET 中构建和开发基于微服务的容器化应用</span><span class="sxs-lookup"><span data-stu-id="1228c-125">Architecting and Developing Containerized Microservice Based Apps in .NET</span></span>
> - <span data-ttu-id="1228c-126">电子书</span><span class="sxs-lookup"><span data-stu-id="1228c-126">**e-book**</span></span>  
> <span data-ttu-id="1228c-127"><http://aka.ms/MicroservicesEbook></span><span class="sxs-lookup"><span data-stu-id="1228c-127"><http://aka.ms/MicroservicesEbook></span></span>
> - <span data-ttu-id="1228c-128">示例应用程序</span><span class="sxs-lookup"><span data-stu-id="1228c-128">**Sample Application**</span></span>  
> <span data-ttu-id="1228c-129"><http://aka.ms/microservicesarchitecture></span><span class="sxs-lookup"><span data-stu-id="1228c-129"><http://aka.ms/microservicesarchitecture></span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="1228c-130">本指南的目标读者</span><span class="sxs-lookup"><span data-stu-id="1228c-130">Who should use this guide</span></span>

<span data-ttu-id="1228c-131">本指南的受众主要是对使用云中的 Microsoft 技术和服务生成新式 web 应用程序感兴趣的开发者、开发潜在顾客和架构师。</span><span class="sxs-lookup"><span data-stu-id="1228c-131">The audience for this guide is mainly developers, development leads, and architects who are interested in building modern web applications using Microsoft technologies and services in the cloud.</span></span>

<span data-ttu-id="1228c-132">次要受众是技术决策制定者，他们已经熟悉 ASP.NET 和/或 Azure，并想要了解是否需要为新项目或现有项目升级到 ASP.NET Core。</span><span class="sxs-lookup"><span data-stu-id="1228c-132">A secondary audience is technical decision makers who are already familiar ASP.NET and/or Azure and are looking for information on whether it makes sense to upgrade to ASP.NET Core for new or existing projects.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="1228c-133">如何使用本指南</span><span class="sxs-lookup"><span data-stu-id="1228c-133">How you can use this guide</span></span>

<span data-ttu-id="1228c-134">本指南已精简为较小的文档，侧重介绍如何使用新式 .NET 技术和 Windows Azure 生成 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1228c-134">This guide has been condensed into a relatively small document that focuses on building web applications with modern .NET technologies and Windows Azure.</span></span> <span data-ttu-id="1228c-135">可通读本指南，了解有关此类应用程序及其技术注意事项的基本信息。</span><span class="sxs-lookup"><span data-stu-id="1228c-135">As such, it can be read in its entirety to provide a foundation of understanding such applications and their technical considerations.</span></span> <span data-ttu-id="1228c-136">本指南及其示例应用程序还可作为操作起点或参考。</span><span class="sxs-lookup"><span data-stu-id="1228c-136">The guide, along with its sample application, can also serve as a starting point or reference.</span></span> <span data-ttu-id="1228c-137">可将相关示例应用程序作为你自己的应用程序的模板，或者了解如何组织应用程序的组件部件。</span><span class="sxs-lookup"><span data-stu-id="1228c-137">Use the associated sample application as a template for your own applications, or to see how you might organize your application's component parts.</span></span> <span data-ttu-id="1228c-138">在对自己的应用程序进行选择权衡时，请参考指南的原则、体系结构的范围以及技术选项和决策注意事项。</span><span class="sxs-lookup"><span data-stu-id="1228c-138">Refer back to the guide's principles and coverage of architecture and technology options and decision considerations when weighing these choices for your own application.</span></span>

<span data-ttu-id="1228c-139">请将本指南转发到团队中，这有助于确保对这些注意事项和机会的共同理解。</span><span class="sxs-lookup"><span data-stu-id="1228c-139">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="1228c-140">确保每个人使用共同的术语和基础原则工作，这有助于构建模式和做法的一致应用。</span><span class="sxs-lookup"><span data-stu-id="1228c-140">Having everybody working from a common set of terminology and underlying principles will help ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="1228c-141">参考资料</span><span class="sxs-lookup"><span data-stu-id="1228c-141">References</span></span>
- <span data-ttu-id="1228c-142">**为服务器应用选择 .NET Core 或 .NET Framework**</span><span class="sxs-lookup"><span data-stu-id="1228c-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
<span data-ttu-id="1228c-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span><span class="sxs-lookup"><span data-stu-id="1228c-143"><https://docs.microsoft.com/dotnet/articles/standard/choosing-core-framework-server></span></span>

>[!div class="step-by-step"]
<span data-ttu-id="1228c-144">[下一个] (modern-web-applications-characteristics.md)</span><span class="sxs-lookup"><span data-stu-id="1228c-144">[Next] (modern-web-applications-characteristics.md)</span></span>
