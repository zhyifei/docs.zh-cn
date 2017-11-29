---
title: "WCF Web HTTP 编程模型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- web services programming model [WCF]
- POX
- REST
ms.assetid: 2312a8d3-b66e-4623-ba42-978434300c7f
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f51ad4a228de0a4a2fae0fb325d045bb09263b3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="wcf-web-http-programming-model"></a><span data-ttu-id="e1faa-102">WCF Web HTTP 编程模型</span><span class="sxs-lookup"><span data-stu-id="e1faa-102">WCF Web HTTP Programming Model</span></span>
<span data-ttu-id="e1faa-103">开发人员使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP 编程模型可以向非 SOAP 终结点公开 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务操作。</span><span class="sxs-lookup"><span data-stu-id="e1faa-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model allows developers to expose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service operations to non-SOAP endpoints.</span></span> <span data-ttu-id="e1faa-104">本节中的主题详细研究此功能。</span><span class="sxs-lookup"><span data-stu-id="e1faa-104">The topics in this section examine the feature in detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1faa-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="e1faa-105">In This Section</span></span>  
 [<span data-ttu-id="e1faa-106">WCF Web HTTP 编程模型概述</span><span class="sxs-lookup"><span data-stu-id="e1faa-106">WCF Web HTTP Programming Model Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model-overview.md)  
 <span data-ttu-id="e1faa-107">概述 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP 编程模型。</span><span class="sxs-lookup"><span data-stu-id="e1faa-107">Provides an overview of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model.</span></span>  
  
 [<span data-ttu-id="e1faa-108">WCF Web HTTP 编程对象模型</span><span class="sxs-lookup"><span data-stu-id="e1faa-108">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)  
 <span data-ttu-id="e1faa-109">讨论 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP 编程模型及其工作方式。</span><span class="sxs-lookup"><span data-stu-id="e1faa-109">Discusses the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web HTTP Programming Model and how it works.</span></span>  
  
 [<span data-ttu-id="e1faa-110">如何： 创建基本 WCF Web HTTP 服务</span><span class="sxs-lookup"><span data-stu-id="e1faa-110">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
 <span data-ttu-id="e1faa-111">说明如何编写公开非 SOAP 终结点的基本服务。</span><span class="sxs-lookup"><span data-stu-id="e1faa-111">Describes how to write a basic service that exposes a non-SOAP endpoint.</span></span>  
  
 [<span data-ttu-id="e1faa-112">如何： 向 SOAP 和 Web 客户端公开协定</span><span class="sxs-lookup"><span data-stu-id="e1faa-112">How to: Expose a Contract to SOAP and Web Clients</span></span>](../../../../docs/framework/wcf/feature-details/how-to-expose-a-contract-to-soap-and-web-clients.md)  
 <span data-ttu-id="e1faa-113">说明如何编写向 SOAP 和非 SOAP 客户端公开同一协定的基本服务。</span><span class="sxs-lookup"><span data-stu-id="e1faa-113">Describes how to write a basic service that exposes the same contract to both SOAP and non-SOAP clients.</span></span>  
  
 [<span data-ttu-id="e1faa-114">UriTemplate 和 UriTemplateTable</span><span class="sxs-lookup"><span data-stu-id="e1faa-114">UriTemplate and UriTemplateTable</span></span>](../../../../docs/framework/wcf/feature-details/uritemplate-and-uritemplatetable.md)  
 <span data-ttu-id="e1faa-115">说明如何使用 <xref:System.UriTemplate> 和 <xref:System.UriTemplateTable> 控制 URI。</span><span class="sxs-lookup"><span data-stu-id="e1faa-115">Describes how to control URIs using <xref:System.UriTemplate> and <xref:System.UriTemplateTable>.</span></span>  
  
 [<span data-ttu-id="e1faa-116">WCF Web HTTP 服务缓存支持</span><span class="sxs-lookup"><span data-stu-id="e1faa-116">Caching Support for WCF Web HTTP Services</span></span>](../../../../docs/framework/wcf/feature-details/caching-support-for-wcf-web-http-services.md)  
 <span data-ttu-id="e1faa-117">说明如何指定 WCF Web HTTP 服务的缓存行为。</span><span class="sxs-lookup"><span data-stu-id="e1faa-117">Describes how to specify caching behavior for a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="e1faa-118">WCF Web HTTP 格式设置</span><span class="sxs-lookup"><span data-stu-id="e1faa-118">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 <span data-ttu-id="e1faa-119">说明如何指定 WCF Web HTTP 服务响应的格式。</span><span class="sxs-lookup"><span data-stu-id="e1faa-119">Describes how to specify the format of the response from a WCF Web HTTP service.</span></span>  
  
 [<span data-ttu-id="e1faa-120">WCF Web HTTP 错误处理</span><span class="sxs-lookup"><span data-stu-id="e1faa-120">WCF Web HTTP Error Handling</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-error-handling.md)  
 <span data-ttu-id="e1faa-121">说明如何将错误返回 WCF Web 客户端，包括 HTTP 状态代码和用户定义的其他错误数据。</span><span class="sxs-lookup"><span data-stu-id="e1faa-121">Describes how to return errors to WCF Web clients including HTTP status codes and additional user-defined error data.</span></span>  
  
 [<span data-ttu-id="e1faa-122">从 WCF 服务调用 REST 样式服务</span><span class="sxs-lookup"><span data-stu-id="e1faa-122">Calling a REST-style service from a WCF service</span></span>](../../../../docs/framework/wcf/feature-details/calling-a-rest-style-service-from-a-wcf-service.md)  
 <span data-ttu-id="e1faa-123">说明如何从 WCF 服务内部来调用 REST 样式服务。</span><span class="sxs-lookup"><span data-stu-id="e1faa-123">Describes how to call a REST-style service from inside a WCF service.</span></span>
