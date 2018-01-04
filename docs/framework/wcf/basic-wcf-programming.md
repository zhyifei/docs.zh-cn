---
title: "基本 WCF 编程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- basic programming [WCF]
- WCF [WCF], basic programming
- WCF [WCF], programming
- Windows Communication Foundation [WCF], basic programming
- Windows Communication Foundation [WCF], programming
ms.assetid: 3ae3d498-f43c-4ecc-8cc0-6cbe36b62593
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfcd0a09f247077f299d8b9c14a07bdc667245b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="basic-wcf-programming"></a><span data-ttu-id="d3829-102">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="d3829-102">Basic WCF Programming</span></span>
<span data-ttu-id="d3829-103">本节介绍创建 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 应用程序的基础知识。</span><span class="sxs-lookup"><span data-stu-id="d3829-103">This section presents the fundamentals for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3829-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="d3829-104">In This Section</span></span>  
 [<span data-ttu-id="d3829-105">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="d3829-105">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
 <span data-ttu-id="d3829-106">描述设计、生成和部署 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务和客户端应用程序的生命周期。</span><span class="sxs-lookup"><span data-stu-id="d3829-106">Describes the lifecycle of designing, building, and deploying [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service and client applications.</span></span>  
  
 [<span data-ttu-id="d3829-107">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="d3829-107">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 <span data-ttu-id="d3829-108">描述如何设计和实现服务协定、选择消息交换模式、指定错误协定，以及服务的其他基本方面。</span><span class="sxs-lookup"><span data-stu-id="d3829-108">Describes how to design and implement a service contract, choose a message exchange pattern, specify a fault contract, and other basic aspects of services.</span></span>  
  
 [<span data-ttu-id="d3829-109">配置服务</span><span class="sxs-lookup"><span data-stu-id="d3829-109">Configuring Services</span></span>](../../../docs/framework/wcf/configuring-services.md)  
 <span data-ttu-id="d3829-110">描述如何配置 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务以支持协定要求、自定义本地运行时行为，以及指示地址以发布服务。</span><span class="sxs-lookup"><span data-stu-id="d3829-110">Describes how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to support the contract requirements, customize local runtime behavior, and indicate the address to publish the service.</span></span>  
  
 [<span data-ttu-id="d3829-111">托管服务</span><span class="sxs-lookup"><span data-stu-id="d3829-111">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 <span data-ttu-id="d3829-112">描述应用程序中宿主服务的基础知识。</span><span class="sxs-lookup"><span data-stu-id="d3829-112">Describes the basics of hosting services in an application.</span></span>  
  
 [<span data-ttu-id="d3829-113">生成客户端</span><span class="sxs-lookup"><span data-stu-id="d3829-113">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
 <span data-ttu-id="d3829-114">描述如何从服务获取元数据、将其转换为 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端代码、处理安全问题，以及生成、配置和承载 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端。</span><span class="sxs-lookup"><span data-stu-id="d3829-114">Describes how to obtain metadata from services, convert that into [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client code, handle security issues, and build, configure, and host an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client.</span></span>  
  
 [<span data-ttu-id="d3829-115">扩展性简介</span><span class="sxs-lookup"><span data-stu-id="d3829-115">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
 <span data-ttu-id="d3829-116">描述如何扩展 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 以创建自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="d3829-116">Describes how to extend [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] to create custom solutions.</span></span>  
  
 [<span data-ttu-id="d3829-117">WCF 疑难解答快速入门</span><span class="sxs-lookup"><span data-stu-id="d3829-117">WCF Troubleshooting Quickstart</span></span>](../../../docs/framework/wcf/wcf-troubleshooting-quickstart.md)  
 <span data-ttu-id="d3829-118">描述一些发生的最常见问题、相应的解决办法以及在哪里可找到有关这些问题的更多信息。</span><span class="sxs-lookup"><span data-stu-id="d3829-118">Describes some of the most common issues that occur, what you can do to solve them, and where to locate more information about the issue.</span></span>  
  
 [<span data-ttu-id="d3829-119">WCF 和 ASP.NET Web API</span><span class="sxs-lookup"><span data-stu-id="d3829-119">WCF and ASP.NET Web API</span></span>](../../../docs/framework/wcf/wcf-and-aspnet-web-api.md)  
 <span data-ttu-id="d3829-120">讨论这两种技术、它们如何相关以及何时使用。</span><span class="sxs-lookup"><span data-stu-id="d3829-120">Discusses the two technologies, how they relate to each other, and when to use them.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="d3829-121">参考</span><span class="sxs-lookup"><span data-stu-id="d3829-121">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="d3829-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="d3829-122">Related Sections</span></span>  
 [<span data-ttu-id="d3829-123">系统要求</span><span class="sxs-lookup"><span data-stu-id="d3829-123">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)  
  
 [<span data-ttu-id="d3829-124">概念性概述</span><span class="sxs-lookup"><span data-stu-id="d3829-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="d3829-125">入门教程</span><span class="sxs-lookup"><span data-stu-id="d3829-125">Getting Started Tutorial</span></span>](../../../docs/framework/wcf/getting-started-tutorial.md)  
  
 [<span data-ttu-id="d3829-126">指南与最佳做法</span><span class="sxs-lookup"><span data-stu-id="d3829-126">Guidelines and Best Practices</span></span>](../../../docs/framework/wcf/guidelines-and-best-practices.md)  
  
 [<span data-ttu-id="d3829-127">Windows Communication Foundation 工具</span><span class="sxs-lookup"><span data-stu-id="d3829-127">Windows Communication Foundation Tools</span></span>](../../../docs/framework/wcf/tools.md)  
  
 [<span data-ttu-id="d3829-128">Windows Communication Foundation 示例</span><span class="sxs-lookup"><span data-stu-id="d3829-128">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
  
 [<span data-ttu-id="d3829-129">入门</span><span class="sxs-lookup"><span data-stu-id="d3829-129">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
  
 [<span data-ttu-id="d3829-130">使用内联代码的 IIS 承载</span><span class="sxs-lookup"><span data-stu-id="d3829-130">IIS Hosting Using Inline Code</span></span>](../../../docs/framework/wcf/samples/iis-hosting-using-inline-code.md)  
  
 [<span data-ttu-id="d3829-131">自承载</span><span class="sxs-lookup"><span data-stu-id="d3829-131">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
