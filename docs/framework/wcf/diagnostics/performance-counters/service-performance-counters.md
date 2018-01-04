---
title: "服务性能计数器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4210f549-31f2-4ea7-99bd-69eaffb98ddf
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8145ff12f5a9befdef3cbf5edf69e5162c4d7014
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="service-performance-counters"></a><span data-ttu-id="bad5c-102">服务性能计数器</span><span class="sxs-lookup"><span data-stu-id="bad5c-102">Service Performance Counters</span></span>
<span data-ttu-id="bad5c-103">服务性能计数器将服务行为作为整体来进行衡量，可用于诊断服务整体性能。</span><span class="sxs-lookup"><span data-stu-id="bad5c-103">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="bad5c-104">如果使用性能监视器 (Perfmon.exe) 查看，可以在 `ServiceModelService 4.0.0.0` 性能对象下找到服务性能计数器。</span><span class="sxs-lookup"><span data-stu-id="bad5c-104">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="bad5c-105">使用以下模式命名计数器实例：</span><span class="sxs-lookup"><span data-stu-id="bad5c-105">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
> [!CAUTION]
>  <span data-ttu-id="bad5c-106">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="bad5c-106">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="bad5c-107">当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 计数器实例名称超出最大长度时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 会用一个哈希值替换实例名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="bad5c-107">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bad5c-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bad5c-108">See Also</span></span>  
 [<span data-ttu-id="bad5c-109">性能计数器</span><span class="sxs-lookup"><span data-stu-id="bad5c-109">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
