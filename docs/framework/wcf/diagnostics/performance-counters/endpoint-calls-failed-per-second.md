---
title: 终结点：Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
ms.openlocfilehash: 9634f8a170bb2fae2f15c3f00dcabb95d512c74e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321461"
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="66faa-102">终结点：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="66faa-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="66faa-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="66faa-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="66faa-104">描述</span><span class="sxs-lookup"><span data-stu-id="66faa-104">Description</span></span>  
 <span data-ttu-id="66faa-105">一秒钟内通过此终结点收到且具有未处理的异常的调用次数。</span><span class="sxs-lookup"><span data-stu-id="66faa-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="66faa-106">此计数器的性能计数器类型为[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="66faa-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="66faa-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="66faa-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="66faa-108">每当此终结点处有未处理的异常时，此计数器就会增加。</span><span class="sxs-lookup"><span data-stu-id="66faa-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66faa-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="66faa-109">See also</span></span>

- [<span data-ttu-id="66faa-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="66faa-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
