---
title: "相关性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
caps.latest.revision: "26"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d15609db250e4743ae2a7a1b6c3c355600704f02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="correlation"></a><span data-ttu-id="e1c92-102">相关性</span><span class="sxs-lookup"><span data-stu-id="e1c92-102">Correlation</span></span>
<span data-ttu-id="e1c92-103">当工作流服务应用程序与其他服务通信时，将这些服务之间的消息调度到适当的工作流实例非常重要。</span><span class="sxs-lookup"><span data-stu-id="e1c92-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="e1c92-104">相关性提供了此调度机制。</span><span class="sxs-lookup"><span data-stu-id="e1c92-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="e1c92-105">本节中的主题概述了相关性以及如何在不同工作流服务方案中使用相关性。</span><span class="sxs-lookup"><span data-stu-id="e1c92-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e1c92-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="e1c92-106">In This Section</span></span>  
 [<span data-ttu-id="e1c92-107">相关概述</span><span class="sxs-lookup"><span data-stu-id="e1c92-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="e1c92-108">提供 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]中可用的相关性类型的概述。</span><span class="sxs-lookup"><span data-stu-id="e1c92-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="e1c92-109">上下文交换</span><span class="sxs-lookup"><span data-stu-id="e1c92-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="e1c92-110">描述上下文交换相关性。</span><span class="sxs-lookup"><span data-stu-id="e1c92-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="e1c92-111">持久双工</span><span class="sxs-lookup"><span data-stu-id="e1c92-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="e1c92-112">描述持久双工相关性。</span><span class="sxs-lookup"><span data-stu-id="e1c92-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="e1c92-113">基于内容</span><span class="sxs-lookup"><span data-stu-id="e1c92-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="e1c92-114">描述基于内容的相关性。</span><span class="sxs-lookup"><span data-stu-id="e1c92-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="e1c92-115">请求-答复</span><span class="sxs-lookup"><span data-stu-id="e1c92-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="e1c92-116">描述请求-答复相关性。</span><span class="sxs-lookup"><span data-stu-id="e1c92-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="e1c92-117">相关问题进行疑难解答</span><span class="sxs-lookup"><span data-stu-id="e1c92-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="e1c92-118">为相关性疑难解答提供方法。</span><span class="sxs-lookup"><span data-stu-id="e1c92-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1c92-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1c92-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="e1c92-120">基于内容的相关性</span><span class="sxs-lookup"><span data-stu-id="e1c92-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="e1c92-121">相关的计算器</span><span class="sxs-lookup"><span data-stu-id="e1c92-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
