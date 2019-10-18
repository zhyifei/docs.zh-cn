---
title: 服务：Calls Failed Per Second（每秒失败的调用次数）
ms.date: 03/30/2017
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
ms.openlocfilehash: 5431144a4618b146a10dfaa3bbdaae34c519319e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72315784"
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="c9be3-102">服务：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="c9be3-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="c9be3-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="c9be3-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="c9be3-104">描述</span><span class="sxs-lookup"><span data-stu-id="c9be3-104">Description</span></span>  
 <span data-ttu-id="c9be3-105">一秒钟内由此服务收到且具有未处理异常的调用次数。</span><span class="sxs-lookup"><span data-stu-id="c9be3-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="c9be3-106">此计数器的性能计数器类型为[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="c9be3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="c9be3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="c9be3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="c9be3-108">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="c9be3-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="c9be3-109">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="c9be3-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="c9be3-110">此服务中每出现一个未处理异常，此计数器就会递增。</span><span class="sxs-lookup"><span data-stu-id="c9be3-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9be3-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9be3-111">See also</span></span>

- [<span data-ttu-id="c9be3-112">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="c9be3-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../specifying-and-handling-faults-in-contracts-and-services.md)
