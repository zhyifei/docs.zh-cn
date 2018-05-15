---
title: 服务性能计数器
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: bdc68fd2b629c538c097dab4e1cf3f89b7f3a091
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="service-performance-counters"></a><span data-ttu-id="c1a2a-102">服务性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1a2a-102">Service Performance Counters</span></span>
<span data-ttu-id="c1a2a-103">服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。</span><span class="sxs-lookup"><span data-stu-id="c1a2a-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="c1a2a-104">如果使用性能监视器 (Perfmon.exe) 查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。</span><span class="sxs-lookup"><span data-stu-id="c1a2a-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="c1a2a-105">使用以下模式命名计数器实例：</span><span class="sxs-lookup"><span data-stu-id="c1a2a-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="c1a2a-106">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="c1a2a-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="c1a2a-107">Windows Communication Foundation (WCF) 计数器实例名称超出最大长度，WCF 会将哈希值替换实例名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1a2a-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a2a-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1a2a-108">See Also</span></span>  
 [<span data-ttu-id="c1a2a-109">性能计数器</span><span class="sxs-lookup"><span data-stu-id="c1a2a-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
