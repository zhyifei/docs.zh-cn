---
title: 终结点性能计数器
ms.date: 03/30/2017
ms.assetid: 7d44d576-bd4e-453b-8b76-a818ce90b806
ms.openlocfilehash: de750b3e5ee61b6bfc5b387fb7de84b74171d8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501956"
---
# <a name="endpoint-performance-counters"></a><span data-ttu-id="3eb58-102">终结点性能计数器</span><span class="sxs-lookup"><span data-stu-id="3eb58-102">Endpoint Performance Counters</span></span>
<span data-ttu-id="3eb58-103">终结点性能计数器可以捕获能够揭示终结点如何接受消息的数据。</span><span class="sxs-lookup"><span data-stu-id="3eb58-103">Endpoint performance counters capture data that reveals how an endpoint is accepting messages.</span></span> <span data-ttu-id="3eb58-104">如果使用性能监视器查看，可以在 `ServiceModelEndpoint 4.0.0.0` 性能对象下找到它们。</span><span class="sxs-lookup"><span data-stu-id="3eb58-104">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="3eb58-105">性能计数器实例使用以下模式命名：</span><span class="sxs-lookup"><span data-stu-id="3eb58-105">The instances are named using this pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="3eb58-106">它们所捕获的数据与针对单个操作收集的数据类似，不同之处仅在于在整个终结点中进行了聚合。</span><span class="sxs-lookup"><span data-stu-id="3eb58-106">The data is similar to that collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="3eb58-107">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="3eb58-107">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="3eb58-108">当 Windows Communication Foundation (WCF) 计数器实例名称超出了最大长度时，WCF 会将实例名称的一部分替换为哈希值。</span><span class="sxs-lookup"><span data-stu-id="3eb58-108">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eb58-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="3eb58-109">See also</span></span>
- [<span data-ttu-id="3eb58-110">性能计数器</span><span class="sxs-lookup"><span data-stu-id="3eb58-110">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
