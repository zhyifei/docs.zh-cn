---
title: 操作性能计数器
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: d4f5755129fecb62e6a4da98a2bf642c5e20f9c1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59077103"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="aedec-102">操作性能计数器</span><span class="sxs-lookup"><span data-stu-id="aedec-102">Operation Performance Counters</span></span>
<span data-ttu-id="aedec-103">使用性能监视器 (Perfmon.exe) 查看时，可以在 `ServiceModelOperation 4.0.0.0` 性能对象下找到操作性能计数器。</span><span class="sxs-lookup"><span data-stu-id="aedec-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="aedec-104">每个操作都有一个单独的实例。</span><span class="sxs-lookup"><span data-stu-id="aedec-104">Each operation has an individual instance.</span></span> <span data-ttu-id="aedec-105">也就是说，如果给定的协定具有 10 个操作，则有 10 个操作计数器实例与该协定相关联。</span><span class="sxs-lookup"><span data-stu-id="aedec-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="aedec-106">对象实例按下面的模式命名：</span><span class="sxs-lookup"><span data-stu-id="aedec-106">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="aedec-107">使用此计数器可以衡量调用的使用方式以及操作的执行情况。</span><span class="sxs-lookup"><span data-stu-id="aedec-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="aedec-108">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="aedec-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="aedec-109">当 Windows Communication Foundation (WCF) 计数器实例名称超出了最大长度时，WCF 会将实例名称的一部分替换为哈希值。</span><span class="sxs-lookup"><span data-stu-id="aedec-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedec-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="aedec-110">See also</span></span>

- [<span data-ttu-id="aedec-111">性能计数器</span><span class="sxs-lookup"><span data-stu-id="aedec-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
