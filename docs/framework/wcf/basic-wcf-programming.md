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
ms.openlocfilehash: cbdc693197344fe570c1462f6ca3115018eb69d6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="c7626-102">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="c7626-102">Basic WCF Programming</span></span>
<span data-ttu-id="c7626-103">本部分介绍用于创建 Windows Communication Foundation (WCF) 应用程序的基础知识。</span><span class="sxs-lookup"><span data-stu-id="c7626-103">This section presents the fundamentals for creating Windows Communication Foundation (WCF) applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7626-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="c7626-104">In This Section</span></span>  
 [<span data-ttu-id="c7626-105">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="c7626-105">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 <span data-ttu-id="c7626-106">描述设计、 构建和部署 WCF 服务和客户端应用程序的生命周期。</span><span class="sxs-lookup"><span data-stu-id="c7626-106">Describes the lifecycle of designing, building, and deploying WCF service and client applications.</span></span>  
  
 [<span data-ttu-id="c7626-107">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="c7626-107">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 <span data-ttu-id="c7626-108">描述如何设计和实现服务协定、选择消息交换模式、指定错误协定，以及服务的其他基本方面。</span><span class="sxs-lookup"><span data-stu-id="c7626-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>  
  
 [<span data-ttu-id="c7626-109">配置服务</span><span class="sxs-lookup"><span data-stu-id="c7626-109">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 <span data-ttu-id="c7626-110">描述如何配置 WCF 服务以支持协定需求、 自定义本地运行时行为，以及指示地址以发布服务。</span><span class="sxs-lookup"><span data-stu-id="c7626-110">Describes how to configure a WCF service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>  
  
 [<span data-ttu-id="c7626-111">托管服务</span><span class="sxs-lookup"><span data-stu-id="c7626-111">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 <span data-ttu-id="c7626-112">描述应用程序中宿主服务的基础知识。</span><span class="sxs-lookup"><span data-stu-id="c7626-112">Describes the basics of hosting services in an application.</span></span>  
  
 [<span data-ttu-id="c7626-113">生成客户端</span><span class="sxs-lookup"><span data-stu-id="c7626-113">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 <span data-ttu-id="c7626-114">描述如何从服务获取元数据、 将其转换到 WCF 客户端代码、 处理安全问题，以及生成、 配置和承载 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="c7626-114">Describes how to obtain metadata from services, convert that into WCF client code, handle security issues, and build, configure, and host an WCF client.</span></span>  
  
 [<span data-ttu-id="c7626-115">扩展性简介</span><span class="sxs-lookup"><span data-stu-id="c7626-115">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
 <span data-ttu-id="c7626-116">描述如何扩展 WCF 创建自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="c7626-116">Describes how to extend WCF to create custom solutions.</span></span>  
  
 [<span data-ttu-id="c7626-117">WCF 疑难解答快速入门</span><span class="sxs-lookup"><span data-stu-id="c7626-117">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 <span data-ttu-id="c7626-118">描述一些发生的最常见问题、相应的解决办法以及在哪里可找到有关这些问题的更多信息。</span><span class="sxs-lookup"><span data-stu-id="c7626-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>  
  
 [<span data-ttu-id="c7626-119">WCF 和 ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="c7626-119">WCF and ASP.NET Web API</span></span>](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)  
 <span data-ttu-id="c7626-120">讨论这两种技术、它们如何相关以及何时使用。</span><span class="sxs-lookup"><span data-stu-id="c7626-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="c7626-121">参考</span><span class="sxs-lookup"><span data-stu-id="c7626-121">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="c7626-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="c7626-122">Related Sections</span></span>  
 [<span data-ttu-id="c7626-123">系统要求</span><span class="sxs-lookup"><span data-stu-id="c7626-123">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)  
  
 [<span data-ttu-id="c7626-124">概念性概述</span><span class="sxs-lookup"><span data-stu-id="c7626-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="c7626-125">入门教程</span><span class="sxs-lookup"><span data-stu-id="c7626-125">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="c7626-126">指南与最佳做法</span><span class="sxs-lookup"><span data-stu-id="c7626-126">Guidelines and Best Practices</span></span>](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
  
 [<span data-ttu-id="c7626-127">Windows Communication Foundation 工具</span><span class="sxs-lookup"><span data-stu-id="c7626-127">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
  
 [<span data-ttu-id="c7626-128">Windows Communication Foundation 示例</span><span class="sxs-lookup"><span data-stu-id="c7626-128">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/library/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="c7626-129">入门</span><span class="sxs-lookup"><span data-stu-id="c7626-129">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
  
 [<span data-ttu-id="c7626-130">使用内联代码的 IIS 承载</span><span class="sxs-lookup"><span data-stu-id="c7626-130">IIS Hosting Using Inline Code</span></span>](../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)  
  
 [<span data-ttu-id="c7626-131">自承载</span><span class="sxs-lookup"><span data-stu-id="c7626-131">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
