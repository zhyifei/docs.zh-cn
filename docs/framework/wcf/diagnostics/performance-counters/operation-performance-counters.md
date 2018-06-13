---
title: 操作性能计数器
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 46b7d5ff071ebf1e3f790a9b56906d9908028ae9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33804412"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="08dee-102">操作性能计数器</span><span class="sxs-lookup"><span data-stu-id="08dee-102">Operation Performance Counters</span></span>
<span data-ttu-id="08dee-103">使用性能监视器 (Perfmon.exe) 查看时，可以在 `ServiceModelOperation 4.0.0.0` 性能对象下找到操作性能计数器。</span><span class="sxs-lookup"><span data-stu-id="08dee-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="08dee-104">每个操作都有一个单独的实例。</span><span class="sxs-lookup"><span data-stu-id="08dee-104">Each operation has an individual instance.</span></span> <span data-ttu-id="08dee-105">也就是说，如果给定的协定具有 10 个操作，则有 10 个操作计数器实例与该协定相关联。</span><span class="sxs-lookup"><span data-stu-id="08dee-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="08dee-106">对象实例按下面的模式命名：</span><span class="sxs-lookup"><span data-stu-id="08dee-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="08dee-107">使用此计数器可以衡量调用的使用方式以及操作的执行情况。</span><span class="sxs-lookup"><span data-stu-id="08dee-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="08dee-108">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="08dee-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="08dee-109">Windows Communication Foundation (WCF) 计数器实例名称超出最大长度，WCF 会将哈希值替换实例名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="08dee-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08dee-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="08dee-110">See Also</span></span>  
 [<span data-ttu-id="08dee-111">性能计数器</span><span class="sxs-lookup"><span data-stu-id="08dee-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
