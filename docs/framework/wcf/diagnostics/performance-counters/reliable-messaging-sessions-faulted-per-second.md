---
title: "Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f8ca2eb-1be4-4b6a-aa78-fcd3ee145fe8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e3a63ba266de8cb4debd8ea43704f9b38049482c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-sessions-faulted-per-second"></a><span data-ttu-id="ce5aa-102">Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）</span><span class="sxs-lookup"><span data-stu-id="ce5aa-102">Reliable Messaging Sessions Faulted Per Second</span></span>
<span data-ttu-id="ce5aa-103">计数器名称：Reliable Messaging Sessions Faulted Per Second（每秒出错的可靠消息会话数）。</span><span class="sxs-lookup"><span data-stu-id="ce5aa-103">Counter Name: Reliable Messaging Sessions Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ce5aa-104">描述</span><span class="sxs-lookup"><span data-stu-id="ce5aa-104">Description</span></span>  
 <span data-ttu-id="ce5aa-105">此服务每秒出错的可靠消息会话的数目。</span><span class="sxs-lookup"><span data-stu-id="ce5aa-105">Number of reliable messaging sessions that are faulted in this service in a second.</span></span>  
  
 <span data-ttu-id="ce5aa-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="ce5aa-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ce5aa-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ce5aa-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
