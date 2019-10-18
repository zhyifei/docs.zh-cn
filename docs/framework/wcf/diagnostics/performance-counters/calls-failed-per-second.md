---
title: Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
ms.openlocfilehash: e7c0b53f4c2b1a7e87a5791b44e452ec9146c459
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321120"
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="6e9e3-102">Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="6e9e3-102">Calls Failed Per Second</span></span>
<span data-ttu-id="6e9e3-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="6e9e3-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e9e3-104">描述</span><span class="sxs-lookup"><span data-stu-id="6e9e3-104">Description</span></span>  
 <span data-ttu-id="6e9e3-105">该操作中每秒钟出现未处理异常的调用数目。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="6e9e3-106">此计数器的性能计数器类型为[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6e9e3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6e9e3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="6e9e3-108">此操作中每次出现未处理的异常时，此计数器都会递增。</span><span class="sxs-lookup"><span data-stu-id="6e9e3-108">This counter is incremented every time there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e9e3-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e9e3-109">See also</span></span>

- [<span data-ttu-id="6e9e3-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="6e9e3-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
