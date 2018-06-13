---
title: 每秒排队病毒消息数
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: 6407cce120f5d534f88a12591ea2ad09bb5130d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33473254"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="b80d9-102">每秒排队病毒消息数</span><span class="sxs-lookup"><span data-stu-id="b80d9-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="b80d9-103">计数器名称：Queued Poison Messages Per Second（每秒排队病毒消息数）。</span><span class="sxs-lookup"><span data-stu-id="b80d9-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b80d9-104">描述</span><span class="sxs-lookup"><span data-stu-id="b80d9-104">Description</span></span>  
 <span data-ttu-id="b80d9-105">此服务中每秒由排队传输标记为病毒消息的消息数。</span><span class="sxs-lookup"><span data-stu-id="b80d9-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="b80d9-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="b80d9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b80d9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b80d9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
