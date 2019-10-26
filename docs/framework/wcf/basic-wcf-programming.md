---
title: 基本 WCF 编程
ms.date: 03/30/2017
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
ms.openlocfilehash: eff565fa18e3360170584395adcf2a3e7029ac07
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960931"
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="3ab68-102">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="3ab68-102">Basic WCF programming</span></span>

<span data-ttu-id="3ab68-103">本部分介绍了创建 Windows Communication Foundation （WCF）应用程序的基础知识。</span><span class="sxs-lookup"><span data-stu-id="3ab68-103">This section presents the fundamentals for creating Windows Communication Foundation (WCF) applications.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3ab68-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="3ab68-104">In this section</span></span>

 <span data-ttu-id="3ab68-105">[基本编程生命周期](basic-programming-lifecycle.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-105">[Basic Programming Lifecycle](basic-programming-lifecycle.md)</span></span>\
 <span data-ttu-id="3ab68-106">介绍设计、生成和部署 WCF 服务和客户端应用程序的生命周期。</span><span class="sxs-lookup"><span data-stu-id="3ab68-106">Describes the lifecycle of designing, building, and deploying WCF service and client applications.</span></span>

 <span data-ttu-id="3ab68-107">[设计和实现服务](designing-and-implementing-services.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-107">[Designing and Implementing Services](designing-and-implementing-services.md)</span></span>\
 <span data-ttu-id="3ab68-108">描述如何设计和实现服务协定、选择消息交换模式、指定错误协定，以及服务的其他基本方面。</span><span class="sxs-lookup"><span data-stu-id="3ab68-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>

 <span data-ttu-id="3ab68-109">[Configuring Services](configuring-services.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-109">[Configuring Services](configuring-services.md)</span></span>\
 <span data-ttu-id="3ab68-110">介绍如何配置 WCF 服务以支持协定要求，自定义本地运行时行为，并指示发布服务的地址。</span><span class="sxs-lookup"><span data-stu-id="3ab68-110">Describes how to configure a WCF service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>

 <span data-ttu-id="3ab68-111">[宿主服务](hosting-services.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-111">[Hosting Services](hosting-services.md)</span></span>\
 <span data-ttu-id="3ab68-112">描述应用程序中宿主服务的基础知识。</span><span class="sxs-lookup"><span data-stu-id="3ab68-112">Describes the basics of hosting services in an application.</span></span>

 <span data-ttu-id="3ab68-113">[生成客户端](building-clients.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-113">[Building Clients](building-clients.md)</span></span>\
 <span data-ttu-id="3ab68-114">描述如何从服务中获取元数据，将其转换为 WCF 客户端代码，处理安全问题，以及生成、配置和托管 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="3ab68-114">Describes how to obtain metadata from services, convert that into WCF client code, handle security issues, and build, configure, and host a WCF client.</span></span>

 <span data-ttu-id="3ab68-115">[扩展性\ 简介](introduction-to-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-115">[Introduction to Extensibility](introduction-to-extensibility.md)\</span></span>
 <span data-ttu-id="3ab68-116">介绍如何扩展 WCF 以创建自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="3ab68-116">Describes how to extend WCF to create custom solutions.</span></span>

 <span data-ttu-id="3ab68-117">[WCF 疑难解答快速入门](wcf-troubleshooting-quickstart.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-117">[WCF Troubleshooting Quickstart](wcf-troubleshooting-quickstart.md)</span></span>\
 <span data-ttu-id="3ab68-118">描述一些发生的最常见问题、相应的解决办法以及在哪里可找到有关这些问题的更多信息。</span><span class="sxs-lookup"><span data-stu-id="3ab68-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>

 <span data-ttu-id="3ab68-119">[WCF 和 ASP.NET Web API](wcf-and-aspnet-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="3ab68-119">[WCF and ASP.NET Web API](wcf-and-aspnet-web-api.md)</span></span>\
 <span data-ttu-id="3ab68-120">讨论这两种技术、它们如何相关以及何时使用。</span><span class="sxs-lookup"><span data-stu-id="3ab68-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>

## <a name="reference"></a><span data-ttu-id="3ab68-121">参考</span><span class="sxs-lookup"><span data-stu-id="3ab68-121">Reference</span></span>

- <xref:System.ServiceModel>
- <xref:System.ServiceModel.Channels>
- <xref:System.ServiceModel.Description>

## <a name="related-sections"></a><span data-ttu-id="3ab68-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="3ab68-122">Related sections</span></span>

- [<span data-ttu-id="3ab68-123">概念性概述</span><span class="sxs-lookup"><span data-stu-id="3ab68-123">Conceptual Overview</span></span>](conceptual-overview.md)
- [<span data-ttu-id="3ab68-124">入门教程</span><span class="sxs-lookup"><span data-stu-id="3ab68-124">Getting Started Tutorial</span></span>](getting-started-tutorial.md)
- [<span data-ttu-id="3ab68-125">指南与最佳做法</span><span class="sxs-lookup"><span data-stu-id="3ab68-125">Guidelines and Best Practices</span></span>](guidelines-and-best-practices.md)
- [<span data-ttu-id="3ab68-126">Windows Communication Foundation 工具</span><span class="sxs-lookup"><span data-stu-id="3ab68-126">Windows Communication Foundation Tools</span></span>](tools.md)
- [<span data-ttu-id="3ab68-127">Windows Communication Foundation （WCF）示例</span><span class="sxs-lookup"><span data-stu-id="3ab68-127">Windows Communication Foundation (WCF) samples</span></span>](./samples/index.md)
- [<span data-ttu-id="3ab68-128">入门</span><span class="sxs-lookup"><span data-stu-id="3ab68-128">Getting Started</span></span>](./samples/getting-started-sample.md)
- [<span data-ttu-id="3ab68-129">使用内联代码的 IIS 承载</span><span class="sxs-lookup"><span data-stu-id="3ab68-129">IIS Hosting Using Inline Code</span></span>](./samples/iis-hosting-using-inline-code.md)
- [<span data-ttu-id="3ab68-130">自承载</span><span class="sxs-lookup"><span data-stu-id="3ab68-130">Self-Host</span></span>](./samples/self-host.md)
