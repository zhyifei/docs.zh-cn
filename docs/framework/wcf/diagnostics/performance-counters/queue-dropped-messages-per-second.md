---
title: 每秒丢弃的排队消息数
ms.date: 03/30/2017
ms.assetid: 74540f52-8762-4147-b5ba-e171180515a3
ms.openlocfilehash: f15b2db08ac4486377189a1533b653260d79024a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418243"
---
# <a name="queue-dropped-messages-per-second"></a><span data-ttu-id="dbb80-102">每秒丢弃的排队消息数</span><span class="sxs-lookup"><span data-stu-id="dbb80-102">Queue Dropped Messages Per Second</span></span>
<span data-ttu-id="dbb80-103">计数器名称：Queued Messages Dropped Per Second（每秒丢弃的排队消息数）。</span><span class="sxs-lookup"><span data-stu-id="dbb80-103">Counter Name: Queued Messages Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="dbb80-104">描述</span><span class="sxs-lookup"><span data-stu-id="dbb80-104">Description</span></span>  
 <span data-ttu-id="dbb80-105">此服务处的排队传输机制每秒丢弃的消息数。</span><span class="sxs-lookup"><span data-stu-id="dbb80-105">Number of messages that are dropped by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="dbb80-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="dbb80-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="dbb80-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="dbb80-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
