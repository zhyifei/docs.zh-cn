---
title: "终结点性能计数器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc5fa1b3600489cb2d5f31c263019ae5006edf65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="debda-102">终结点性能计数器</span><span class="sxs-lookup"><span data-stu-id="debda-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="debda-103">终结点性能计数器可以捕获能够揭示终结点如何接受消息的数据。</span><span class="sxs-lookup"><span data-stu-id="debda-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="debda-104">如果使用性能监视器查看，可以在 `ServiceModelEndpoint 4.0.0.0` 性能对象下找到它们。</span><span class="sxs-lookup"><span data-stu-id="debda-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="debda-105">性能计数器实例使用以下模式命名：</span><span class="sxs-lookup"><span data-stu-id="debda-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="debda-106">它们所捕获的数据与针对单个操作收集的数据类似，不同之处仅在于在整个终结点中进行了聚合。</span><span class="sxs-lookup"><span data-stu-id="debda-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="debda-107">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="debda-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="debda-108">当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 计数器实例名称超出最大长度时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 会用一个哈希值替换实例名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="debda-108">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="debda-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="debda-109">See Also</span></span>  
 [<span data-ttu-id="debda-110">性能计数器</span><span class="sxs-lookup"><span data-stu-id="debda-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
