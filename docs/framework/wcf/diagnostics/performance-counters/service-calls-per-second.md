---
title: "服务：Calls Per Second（每秒调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6261d28d-d449-425a-b9fc-a4ee14079134
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 940249c4ec0317013efcb03aafc11d384ec0363f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-per-second"></a><span data-ttu-id="1e371-102">服务：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="1e371-102">Service: Calls Per Second</span></span>
<span data-ttu-id="1e371-103">计数器名称：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="1e371-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="1e371-104">描述</span><span class="sxs-lookup"><span data-stu-id="1e371-104">Description</span></span>  
 <span data-ttu-id="1e371-105">一秒内调用此服务的次数。</span><span class="sxs-lookup"><span data-stu-id="1e371-105">Number of calls to this service in a second.</span></span>  
  
 <span data-ttu-id="1e371-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="1e371-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1e371-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)。其中，分子 (N) 代表上一个取样时间间隔内执行的操作数，而分母 (D) 代表上一个取样时间间隔内所用的滴答数，而 F 则是滴答频率。</span><span class="sxs-lookup"><span data-stu-id="1e371-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F) where the numerator (N) represents the number of operations performed during the last sample interval, the denominator (D) represents the number of ticks elapsed during the last sample interval, and F is the frequency of the ticks.</span></span>
