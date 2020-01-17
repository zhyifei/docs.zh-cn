---
title: 每秒丢弃的排队消息数
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: 6ec762d7e5dd7daf63b5df76e1ffb48957538538
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164029"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="0a938-102">每秒丢弃的排队消息数</span><span class="sxs-lookup"><span data-stu-id="0a938-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="0a938-103">计数器名称：Queued Messages Dropped Per Second（每秒丢弃的排队消息数）。</span><span class="sxs-lookup"><span data-stu-id="0a938-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="0a938-104">描述</span><span class="sxs-lookup"><span data-stu-id="0a938-104">Description</span></span>  
 <span data-ttu-id="0a938-105">此服务处的排队传输机制每秒丢弃的消息数。</span><span class="sxs-lookup"><span data-stu-id="0a938-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="0a938-106">此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="0a938-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="0a938-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="0a938-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
