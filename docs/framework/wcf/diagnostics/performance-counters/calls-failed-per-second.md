---
title: Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: aa8cd4c2d9f642b525b2b9ccb931c4f2101a5129
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "67421791"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="23b60-102">Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="23b60-102">Calls Failed Per Second</span></span>
<span data-ttu-id="23b60-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="23b60-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="23b60-104">描述</span><span class="sxs-lookup"><span data-stu-id="23b60-104">Description</span></span>  
 <span data-ttu-id="23b60-105">该操作中每秒钟出现未处理异常的调用数目。</span><span class="sxs-lookup"><span data-stu-id="23b60-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="23b60-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="23b60-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="23b60-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="23b60-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="23b60-108">此计数器在每次在此操作中出现未处理异常时递增。</span><span class="sxs-lookup"><span data-stu-id="23b60-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23b60-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="23b60-109">See also</span></span>

- [<span data-ttu-id="23b60-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="23b60-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
