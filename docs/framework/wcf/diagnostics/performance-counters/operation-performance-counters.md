---
title: 操作性能计数器
ms.date: 03/30/2017
ms.assetid: 333a51e0-f56e-4e1a-b359-5c91ff390568
ms.openlocfilehash: 31b0f92ae3477bd3c1de8c348a60e5c64d7c53cc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855677"
---
# <a name="operation-performance-counters"></a><span data-ttu-id="f9499-102">操作性能计数器</span><span class="sxs-lookup"><span data-stu-id="f9499-102">Operation Performance Counters</span></span>
<span data-ttu-id="f9499-103">使用性能监视器 (Perfmon.exe) 查看时，可以在 `ServiceModelOperation 4.0.0.0` 性能对象下找到操作性能计数器。</span><span class="sxs-lookup"><span data-stu-id="f9499-103">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor (Perfmon.exe).</span></span> <span data-ttu-id="f9499-104">每个操作都有一个单独的实例。</span><span class="sxs-lookup"><span data-stu-id="f9499-104">Each operation has an individual instance.</span></span> <span data-ttu-id="f9499-105">也就是说，如果给定的协定具有 10 个操作，则有 10 个操作计数器实例与该协定相关联。</span><span class="sxs-lookup"><span data-stu-id="f9499-105">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="f9499-106">对象实例按下面的模式命名：</span><span class="sxs-lookup"><span data-stu-id="f9499-106">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="f9499-107">使用此计数器可以衡量调用的使用方式以及操作的执行情况。</span><span class="sxs-lookup"><span data-stu-id="f9499-107">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="f9499-108">性能计数器实例的名称长度存在限制。</span><span class="sxs-lookup"><span data-stu-id="f9499-108">There is a limit on the length of a performance counter instance's name.</span></span> <span data-ttu-id="f9499-109">当 Windows Communication Foundation （WCF）计数器实例名称超出最大长度时，WCF 会将部分实例名称替换为哈希值。</span><span class="sxs-lookup"><span data-stu-id="f9499-109">When a Windows Communication Foundation (WCF) counter instance name exceeds the maximum length, WCF replaces a portion of the instance name with a hash value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9499-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9499-110">See also</span></span>

- [<span data-ttu-id="f9499-111">性能计数器</span><span class="sxs-lookup"><span data-stu-id="f9499-111">Performance Counters</span></span>](../../../../../docs/framework/wcf/diagnostics/performance-counters/index.md)
