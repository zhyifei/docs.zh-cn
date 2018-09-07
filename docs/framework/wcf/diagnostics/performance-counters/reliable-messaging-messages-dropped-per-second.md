---
title: Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）
ms.date: 03/30/2017
ms.assetid: a11b0b80-b242-48e1-b0bb-7f756db5486b
ms.openlocfilehash: 7722b32f99b302c5c272e095033879c9e04c7ee1
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44075379"
---
# <a name="reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="67096-102">Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）</span><span class="sxs-lookup"><span data-stu-id="67096-102">Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="67096-103">计数器名称：Reliable Messaging Sessions Dropped Per Second（每秒丢弃的可靠消息会话数）。</span><span class="sxs-lookup"><span data-stu-id="67096-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="67096-104">描述</span><span class="sxs-lookup"><span data-stu-id="67096-104">Description</span></span>  
 <span data-ttu-id="67096-105">此服务上每秒钟丢弃的可靠传送消息总数。</span><span class="sxs-lookup"><span data-stu-id="67096-105">Total number of reliable messaging messages that have been dropped in this service in a second.</span></span>  
  
 <span data-ttu-id="67096-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="67096-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="67096-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="67096-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
