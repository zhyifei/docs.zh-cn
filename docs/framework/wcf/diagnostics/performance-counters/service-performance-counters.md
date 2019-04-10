---
title: 服务性能计数器
ms.date: 03/30/2017
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
ms.openlocfilehash: dc31e05f82f232095f6560c8fdd9bf75c040e2ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210407"
---
# <a name="service-performance-counters"></a><span data-ttu-id="0206d-102">服务性能计数器</span><span class="sxs-lookup"><span data-stu-id="0206d-102">Service Performance Counters</span></span>
<span data-ttu-id="0206d-103">服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。</span><span class="sxs-lookup"><span data-stu-id="0206d-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="0206d-104">如果使用性能监视器 (Perfmon.exe) 查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。</span><span class="sxs-lookup"><span data-stu-id="0206d-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="0206d-105">使用以下模式命名计数器实例：</span><span class="sxs-lookup"><span data-stu-id="0206d-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="0206d-106">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="0206d-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="0206d-107">当 Windows Communication Foundation (WCF) 计数器实例名称超出了最大长度时，WCF 会将实例名称的一部分替换为哈希值。</span><span class="sxs-lookup"><span data-stu-id="0206d-107">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0206d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="0206d-108">See also</span></span>

- [<span data-ttu-id="0206d-109">性能计数器</span><span class="sxs-lookup"><span data-stu-id="0206d-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
