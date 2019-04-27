---
title: 每秒丢弃的排队消息数
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916157"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="b7695-102">每秒丢弃的排队消息数</span><span class="sxs-lookup"><span data-stu-id="b7695-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="b7695-103">计数器名称：每秒丢弃的排队的消息。</span><span class="sxs-lookup"><span data-stu-id="b7695-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b7695-104">描述</span><span class="sxs-lookup"><span data-stu-id="b7695-104">Description</span></span>  
 <span data-ttu-id="b7695-105">此服务处的排队传输机制每秒丢弃的消息数。</span><span class="sxs-lookup"><span data-stu-id="b7695-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="b7695-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="b7695-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b7695-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b7695-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
