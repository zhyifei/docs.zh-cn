---
title: Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）
ms.date: 03/30/2017
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
ms.openlocfilehash: c77d6a5f12dcce15dba94e2f63025a219ebcc6fd
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45964600"
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="8b71d-102">Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）</span><span class="sxs-lookup"><span data-stu-id="8b71d-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="8b71d-103">计数器名称：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）。</span><span class="sxs-lookup"><span data-stu-id="8b71d-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="8b71d-104">描述</span><span class="sxs-lookup"><span data-stu-id="8b71d-104">Description</span></span>  
 <span data-ttu-id="8b71d-105">此服务每秒出错的可靠消息会话的数目。</span><span class="sxs-lookup"><span data-stu-id="8b71d-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="8b71d-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="8b71d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="8b71d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="8b71d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
