---
title: 每秒拒绝的排队消息数
ms.date: 03/30/2017
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
ms.openlocfilehash: 096e2188b13d0fd5a9be35e5e6473107a58c5566
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916179"
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="6e853-102">每秒拒绝的排队消息数</span><span class="sxs-lookup"><span data-stu-id="6e853-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="6e853-103">计数器名称：每秒拒绝的排队的消息。</span><span class="sxs-lookup"><span data-stu-id="6e853-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e853-104">描述</span><span class="sxs-lookup"><span data-stu-id="6e853-104">Description</span></span>  
 <span data-ttu-id="6e853-105">此服务中每秒被排队传输拒绝的消息数。</span><span class="sxs-lookup"><span data-stu-id="6e853-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="6e853-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="6e853-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6e853-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="6e853-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
