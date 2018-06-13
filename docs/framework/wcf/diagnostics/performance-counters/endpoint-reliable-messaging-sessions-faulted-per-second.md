---
title: 终结点：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
ms.date: 03/30/2017
ms.assetid: e9ae808a-7e1f-46b0-9560-d5a866be6d6e
ms.openlocfilehash: 198acbeff6b8a54dcc6e4ae6966fea996da4b745
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472766"
---
# <a name="endpoint-reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="d8926-102">终结点：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）</span><span class="sxs-lookup"><span data-stu-id="d8926-102">Endpoint: Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="d8926-103">计数器名称：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）。</span><span class="sxs-lookup"><span data-stu-id="d8926-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="d8926-104">描述</span><span class="sxs-lookup"><span data-stu-id="d8926-104">Description</span></span>  
 <span data-ttu-id="d8926-105">此终结点上每秒出错的可靠消息会话的数量。</span><span class="sxs-lookup"><span data-stu-id="d8926-105">Number of reliable messaging sessions that are faulted at this endpoint in a second.</span></span>  
  
 <span data-ttu-id="d8926-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="d8926-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="d8926-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="d8926-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
