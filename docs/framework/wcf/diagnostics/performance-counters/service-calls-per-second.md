---
title: 服务：Calls Per Second（每秒调用次数）
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: be5d77169a71d6f44205a1150da5239eceff7d9c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163899"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="2c45d-102">服务：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="2c45d-102">Service: Calls Per Second</span></span>
<span data-ttu-id="2c45d-103">计数器名称：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="2c45d-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2c45d-104">描述</span><span class="sxs-lookup"><span data-stu-id="2c45d-104">Description</span></span>  
 <span data-ttu-id="2c45d-105">一秒内调用此服务的次数。</span><span class="sxs-lookup"><span data-stu-id="2c45d-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="2c45d-106">此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="2c45d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2c45d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)。其中，分子 (N) 代表上一个取样时间间隔内执行的操作数，而分母 (D) 代表上一个取样时间间隔内所用的滴答数，而 F 则是滴答频率。</span><span class="sxs-lookup"><span data-stu-id="2c45d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
