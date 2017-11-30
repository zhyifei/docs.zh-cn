---
title: "指南与最佳做法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, guidelines
- best practices [WCF], application design
- Windows Communication Foundation, best practices
- WCF, best practices
- Windows Communication Foundation, guidelines
ms.assetid: 5098ba46-6e8d-4e02-b0c5-d737f9fdad84
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8e2d4bb918946d618aa9253f2c1e27a4566d3d6f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="guidelines-and-best-practices"></a><span data-ttu-id="8365b-102">指南与最佳做法</span><span class="sxs-lookup"><span data-stu-id="8365b-102">Guidelines and Best Practices</span></span>
<span data-ttu-id="8365b-103">本节包含多个主题，这些主题提供了有关创建 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 应用程序的准则。</span><span class="sxs-lookup"><span data-stu-id="8365b-103">This section contains topics that provide guidelines for creating [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8365b-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8365b-104">In This Section</span></span>  
 [<span data-ttu-id="8365b-105">最佳做法：数据协定版本控制</span><span class="sxs-lookup"><span data-stu-id="8365b-105">Best Practices: Data Contract Versioning</span></span>](../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 <span data-ttu-id="8365b-106">说明如何以及何时创建数据协定，使其在更高版本被创建之后不会失效。</span><span class="sxs-lookup"><span data-stu-id="8365b-106">Explains how and when to create data contracts that do not break when future versions are created.</span></span>  
  
 [<span data-ttu-id="8365b-107">服务版本控制</span><span class="sxs-lookup"><span data-stu-id="8365b-107">Service Versioning</span></span>](../../../docs/framework/wcf/service-versioning.md)  
 <span data-ttu-id="8365b-108">说明如何考虑 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中的版本管理。</span><span class="sxs-lookup"><span data-stu-id="8365b-108">Explains how to consider versioning in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="8365b-109">服务（及其公开的终结点）部署之后，可能需要进行更改以达到某些要求，例如，满足不断变化的业务需求或 IT 需求，或者解决问题。</span><span class="sxs-lookup"><span data-stu-id="8365b-109">After deployment, services (and the endpoints they expose) might need to be changed, for example, to satisfy changing business requirements or IT requirements, or to fix issues.</span></span> <span data-ttu-id="8365b-110">每次更改都会引入服务的一个新版本。</span><span class="sxs-lookup"><span data-stu-id="8365b-110">Each change introduces a new version of the service.</span></span>  
  
 [<span data-ttu-id="8365b-111">负载均衡</span><span class="sxs-lookup"><span data-stu-id="8365b-111">Load Balancing</span></span>](../../../docs/framework/wcf/load-balancing.md)  
 <span data-ttu-id="8365b-112">列出使用网络场实现负载平衡的准则。</span><span class="sxs-lookup"><span data-stu-id="8365b-112">Lists guidelines for load balancing with a Web farm.</span></span>  
  
 [<span data-ttu-id="8365b-113">控制资源消耗并提升性能</span><span class="sxs-lookup"><span data-stu-id="8365b-113">Controlling Resource Consumption and Improving Performance</span></span>](../../../docs/framework/wcf/controlling-resource-consumption-and-improving-performance.md)  
 <span data-ttu-id="8365b-114">描述专门用于帮助防止过度消耗资源和提高安全性的属性，并提供指向有关其用法的更详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="8365b-114">Describes the properties that are designed to help prevent undue resource consumption and improve security and points to more complete information about their use.</span></span>  
  
 [<span data-ttu-id="8365b-115">使用 ClickOnce 部署 WCF 应用程序</span><span class="sxs-lookup"><span data-stu-id="8365b-115">Deploying WCF Applications with ClickOnce</span></span>](../../../docs/framework/wcf/deploying-wcf-applications-with-clickonce.md)  
 <span data-ttu-id="8365b-116">描述使用 ClickOnce 功能时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="8365b-116">Describes the considerations to be made when using the ClickOnce feature.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8365b-117">参考</span><span class="sxs-lookup"><span data-stu-id="8365b-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.Runtime.Serialization>  
  
## <a name="related-sections"></a><span data-ttu-id="8365b-118">相关章节</span><span class="sxs-lookup"><span data-stu-id="8365b-118">Related Sections</span></span>  
 [<span data-ttu-id="8365b-119">概念性概述</span><span class="sxs-lookup"><span data-stu-id="8365b-119">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
  
 [<span data-ttu-id="8365b-120">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="8365b-120">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="8365b-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8365b-121">See Also</span></span>  
 [<span data-ttu-id="8365b-122">什么是 Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8365b-122">What Is Windows Communication Foundation</span></span>](../../../docs/framework/wcf/whats-wcf.md)  
 [<span data-ttu-id="8365b-123">Windows Communication Foundation 示例</span><span class="sxs-lookup"><span data-stu-id="8365b-123">Windows Communication Foundation Samples</span></span>](http://msdn.microsoft.com/en-us/8ec9d192-5d81-4f64-bfd3-90c5e5858c91)  
 [<span data-ttu-id="8365b-124">概念性概述</span><span class="sxs-lookup"><span data-stu-id="8365b-124">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="8365b-125">生成客户端</span><span class="sxs-lookup"><span data-stu-id="8365b-125">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)
