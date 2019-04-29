---
title: 每秒排队病毒消息数
ms.date: 03/30/2017
ms.assetid: d193fdd1-02f1-44a0-906e-f632a8f574c3
ms.openlocfilehash: d4c921b105dfd1c1a364d2c86f54ab920078dd4a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916144"
---
# <a name="queued-poison-messages-per-second"></a><span data-ttu-id="51b9d-102">每秒排队病毒消息数</span><span class="sxs-lookup"><span data-stu-id="51b9d-102">Queued Poison Messages Per Second</span></span>
<span data-ttu-id="51b9d-103">计数器名称：每秒排队病毒消息。</span><span class="sxs-lookup"><span data-stu-id="51b9d-103">Counter Name: Queued Poison Messages Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="51b9d-104">描述</span><span class="sxs-lookup"><span data-stu-id="51b9d-104">Description</span></span>  
 <span data-ttu-id="51b9d-105">此服务中每秒由排队传输标记为病毒消息的消息数。</span><span class="sxs-lookup"><span data-stu-id="51b9d-105">Number of messages that are marked poisoned by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="51b9d-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="51b9d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="51b9d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="51b9d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
