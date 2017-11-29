---
title: "Windows Communication Foundation 终结点"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: endpoints [WCF]
ms.assetid: bd0c310f-dd9f-4081-9be2-3db5909850b6
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4ac3d1f16d860ea01217d0d1d35d0588da0c8d87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-endpoints"></a><span data-ttu-id="a97b4-102">Windows Communication Foundation 终结点</span><span class="sxs-lookup"><span data-stu-id="a97b4-102">Windows Communication Foundation Endpoints</span></span>
<span data-ttu-id="a97b4-103">与所有通信[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]服务是通过*终结点*的服务。</span><span class="sxs-lookup"><span data-stu-id="a97b4-103">All communication with a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="a97b4-104">利用终结点，客户端可访问 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务提供的功能。</span><span class="sxs-lookup"><span data-stu-id="a97b4-104">Endpoints provide clients access to the functionality that a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service offers.</span></span>  
  
 <span data-ttu-id="a97b4-105">有关如何创建一个终结点的概述，请参阅[终结点创建概述](../../../docs/framework/wcf/endpoint-creation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a97b4-105">For an overview about how to create an endpoint, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="a97b4-106">每个终结点包含：</span><span class="sxs-lookup"><span data-stu-id="a97b4-106">Each endpoint contains:</span></span>  
  
-   <span data-ttu-id="a97b4-107">一个指示要查找终结点位置的地址。</span><span class="sxs-lookup"><span data-stu-id="a97b4-107">An address that indicates where to find the endpoint.</span></span>  
  
-   <span data-ttu-id="a97b4-108">一个指定客户端如何与终结点进行通信的绑定。</span><span class="sxs-lookup"><span data-stu-id="a97b4-108">A binding that specifies how a client can communicate with the endpoint.</span></span>  
  
-   <span data-ttu-id="a97b4-109">一个标识可用方法的协定。</span><span class="sxs-lookup"><span data-stu-id="a97b4-109">A contract that identifies the methods available.</span></span>  
  
 <span data-ttu-id="a97b4-110">有关如何指定终结点的上述各个部分的说明，请参见：</span><span class="sxs-lookup"><span data-stu-id="a97b4-110">For descriptions about how to specify these individual parts of an endpoint, see:</span></span>  
  
-   [<span data-ttu-id="a97b4-111">指定终结点地址</span><span class="sxs-lookup"><span data-stu-id="a97b4-111">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
  
-   [<span data-ttu-id="a97b4-112">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a97b4-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
  
-   [<span data-ttu-id="a97b4-113">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="a97b4-113">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="in-this-section"></a><span data-ttu-id="a97b4-114">本节内容</span><span class="sxs-lookup"><span data-stu-id="a97b4-114">In This Section</span></span>  
 [<span data-ttu-id="a97b4-115">终结点创建概述</span><span class="sxs-lookup"><span data-stu-id="a97b4-115">Endpoint Creation Overview</span></span>](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 <span data-ttu-id="a97b4-116">描述终结点的结构，并概述如何在配置和代码中定义终结点，以及如何使用运行时提供的默认终结点、绑定和行为。</span><span class="sxs-lookup"><span data-stu-id="a97b4-116">Describes the structure of an endpoint and outlines how to define an endpoint in configuration and in code, as well as how to use the default endpoints, bindings, and behaviors provided by the runtime.</span></span>  
  
 [<span data-ttu-id="a97b4-117">指定终结点地址</span><span class="sxs-lookup"><span data-stu-id="a97b4-117">Specifying an Endpoint Address</span></span>](../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 <span data-ttu-id="a97b4-118">描述如何通过终结点与 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="a97b4-118">Describes how communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through endpoints.</span></span>  
  
 [<span data-ttu-id="a97b4-119">如何： 在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="a97b4-119">How to: Create a Service Endpoint in Configuration</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 <span data-ttu-id="a97b4-120">演示如何在配置中创建服务终结点。</span><span class="sxs-lookup"><span data-stu-id="a97b4-120">Demonstrates how to create a service endpoint in configuration.</span></span>  
  
 [<span data-ttu-id="a97b4-121">如何： 在代码中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="a97b4-121">How to: Create a Service Endpoint in Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 <span data-ttu-id="a97b4-122">演示如何在代码中创建服务终结点。</span><span class="sxs-lookup"><span data-stu-id="a97b4-122">Demonstrates how to create a service endpoint in code.</span></span>  
  
 [<span data-ttu-id="a97b4-123">发布元数据终结点</span><span class="sxs-lookup"><span data-stu-id="a97b4-123">Publishing Metadata Endpoints</span></span>](../../../docs/framework/wcf/publishing-metadata-endpoints.md)  
 <span data-ttu-id="a97b4-124">演示如何通过在配置和代码中发布元数据终结点来发布元数据。</span><span class="sxs-lookup"><span data-stu-id="a97b4-124">Demonstrates how to publish metadata by publishing metadata endpoints in configuration and in code.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a97b4-125">参考</span><span class="sxs-lookup"><span data-stu-id="a97b4-125">Reference</span></span>  
 <xref:System.ServiceModel.EndpointAddress>  
  
## <a name="related-sections"></a><span data-ttu-id="a97b4-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="a97b4-126">Related Sections</span></span>  
 [<span data-ttu-id="a97b4-127">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="a97b4-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)
