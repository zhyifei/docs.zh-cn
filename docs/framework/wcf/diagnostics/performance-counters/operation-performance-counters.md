---
title: "操作性能计数器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c752c56fa60cd717f54a7a06d0d3be8b70e7772
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="operation-performance-counters"></a><span data-ttu-id="b762a-102">操作性能计数器</span><span class="sxs-lookup"><span data-stu-id="b762a-102">Operation Performance Counters</span></span>
<span data-ttu-id="b762a-103">使用性能监视器 (Perfmon.exe) 查看时，可以在 `ServiceModelOperation 4.0.0.0` 性能对象下找到操作性能计数器。</span><span class="sxs-lookup"><span data-stu-id="b762a-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="b762a-104">每个操作都有一个单独的实例。</span><span class="sxs-lookup"><span data-stu-id="b762a-104">Each operation has an individual instance.</span></span> <span data-ttu-id="b762a-105">也就是说，如果给定的协定具有 10 个操作，则有 10 个操作计数器实例与该协定相关联。</span><span class="sxs-lookup"><span data-stu-id="b762a-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="b762a-106">对象实例按下面的模式命名：</span><span class="sxs-lookup"><span data-stu-id="b762a-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="b762a-107">使用此计数器可以衡量调用的使用方式以及操作的执行情况。</span><span class="sxs-lookup"><span data-stu-id="b762a-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b762a-108">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="b762a-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="b762a-109">当 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 计数器实例名称超出最大长度时，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 会用一个哈希值替换实例名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="b762a-109">When a [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] counter instance name exceeds the maximum length, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b762a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b762a-110">See Also</span></span>  
 [<span data-ttu-id="b762a-111">性能计数器</span><span class="sxs-lookup"><span data-stu-id="b762a-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
