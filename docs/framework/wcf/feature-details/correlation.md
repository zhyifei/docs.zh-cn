---
title: 相关性
ms.date: 03/30/2017
ms.assetid: 60151f6c-19b7-47af-9cdc-76c2ac95f301
ms.openlocfilehash: 9dbebf6d497a5cc109400d04206d39ad76321ba3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491278"
---
# <a name="correlation"></a><span data-ttu-id="8d3a4-102">相关性</span><span class="sxs-lookup"><span data-stu-id="8d3a4-102">Correlation</span></span>
<span data-ttu-id="8d3a4-103">当工作流服务应用程序与其他服务通信时，将这些服务之间的消息调度到适当的工作流实例非常重要。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-103">When workflow service applications communicate with other services, it is important that messages between them are dispatched to the appropriate workflow instance.</span></span> <span data-ttu-id="8d3a4-104">相关性提供了此调度机制。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-104">Correlation provides the mechanism for this.</span></span> <span data-ttu-id="8d3a4-105">本节中的主题概述了相关性以及如何在不同工作流服务方案中使用相关性。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-105">The topics in this section provide an overview of correlation and how to use it in different workflow service scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d3a4-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d3a4-106">In This Section</span></span>  
 [<span data-ttu-id="8d3a4-107">关联概述</span><span class="sxs-lookup"><span data-stu-id="8d3a4-107">Correlation Overview</span></span>](../../../../docs/framework/wcf/feature-details/correlation-overview.md)  
 <span data-ttu-id="8d3a4-108">提供 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]中可用的相关性类型的概述。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-108">Provides an overview of the types of correlation available in [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="8d3a4-109">上下文交换</span><span class="sxs-lookup"><span data-stu-id="8d3a4-109">Context Exchange</span></span>](../../../../docs/framework/wcf/feature-details/context-exchange-correlation.md)  
 <span data-ttu-id="8d3a4-110">描述上下文交换相关性。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-110">Describes context exchange correlation.</span></span>  
  
 [<span data-ttu-id="8d3a4-111">持久双工</span><span class="sxs-lookup"><span data-stu-id="8d3a4-111">Durable Duplex</span></span>](../../../../docs/framework/wcf/feature-details/durable-duplex-correlation.md)  
 <span data-ttu-id="8d3a4-112">描述持久双工相关性。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-112">Describes durable duplex correlation.</span></span>  
  
 [<span data-ttu-id="8d3a4-113">基于内容</span><span class="sxs-lookup"><span data-stu-id="8d3a4-113">Content Based</span></span>](../../../../docs/framework/wcf/feature-details/content-based-correlation.md)  
 <span data-ttu-id="8d3a4-114">描述基于内容的相关性。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-114">Describes content-based correlation.</span></span>  
  
 [<span data-ttu-id="8d3a4-115">请求-答复</span><span class="sxs-lookup"><span data-stu-id="8d3a4-115">Request-Reply</span></span>](../../../../docs/framework/wcf/feature-details/request-reply-correlation.md)  
 <span data-ttu-id="8d3a4-116">描述请求-答复相关性。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-116">Describes request-reply correlation.</span></span>  
  
 [<span data-ttu-id="8d3a4-117">关联问题疑难解答</span><span class="sxs-lookup"><span data-stu-id="8d3a4-117">Troubleshooting Correlation</span></span>](../../../../docs/framework/wcf/feature-details/troubleshooting-correlation.md)  
 <span data-ttu-id="8d3a4-118">为相关性疑难解答提供方法。</span><span class="sxs-lookup"><span data-stu-id="8d3a4-118">Provides methods for troubleshooting correlation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d3a4-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d3a4-119">See Also</span></span>  
 <xref:System.ServiceModel.Activities.CorrelationHandle>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.Receive>  
 <xref:System.ServiceModel.CorrelationQuery>  
 [<span data-ttu-id="8d3a4-120">基于内容的关联</span><span class="sxs-lookup"><span data-stu-id="8d3a4-120">Content-Based Correlation</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/content-based-correlation.md)  
 [<span data-ttu-id="8d3a4-121">相关计算器</span><span class="sxs-lookup"><span data-stu-id="8d3a4-121">Correlated Calculator</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/correlated-calculator.md)
