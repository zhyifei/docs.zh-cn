---
title: 终结点：Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863499"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a><span data-ttu-id="795ce-102">终结点：Reliable Messaging Messages Dropped Per Second（每秒丢弃的可靠消息传递消息数）</span><span class="sxs-lookup"><span data-stu-id="795ce-102">Endpoint: Reliable Messaging Messages Dropped Per Second</span></span>
<span data-ttu-id="795ce-103">计数器名称：Reliable Messaging Sessions Dropped Per Second（每秒丢弃的可靠消息会话数）。</span><span class="sxs-lookup"><span data-stu-id="795ce-103">Counter Name: Reliable Messaging Sessions Dropped Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="795ce-104">描述</span><span class="sxs-lookup"><span data-stu-id="795ce-104">Description</span></span>  
 <span data-ttu-id="795ce-105">此终结点上每秒钟丢弃的可靠传送消息总数。</span><span class="sxs-lookup"><span data-stu-id="795ce-105">Total number of reliable messaging messages that have been dropped at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="795ce-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="795ce-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="795ce-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="795ce-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
