---
title: 服务：Calls Per Second（每秒调用次数）
ms.date: 03/30/2017
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
ms.openlocfilehash: 5189a78e2655707d165f187e06ac9a60d055eac0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61773309"
---
# <a name="service-calls-per-second"></a><span data-ttu-id="d3fc0-102">服务：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="d3fc0-102">Service: Calls Per Second</span></span>
<span data-ttu-id="d3fc0-103">计数器名称：每秒调用。</span><span class="sxs-lookup"><span data-stu-id="d3fc0-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d3fc0-104">描述</span><span class="sxs-lookup"><span data-stu-id="d3fc0-104">Description</span></span>  
 <span data-ttu-id="d3fc0-105">一秒内调用此服务的次数。</span><span class="sxs-lookup"><span data-stu-id="d3fc0-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="d3fc0-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="d3fc0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d3fc0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)。其中，分子 (N) 代表上一个取样时间间隔内执行的操作数，而分母 (D) 代表上一个取样时间间隔内所用的滴答数，而 F 则是滴答频率。</span><span class="sxs-lookup"><span data-stu-id="d3fc0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
