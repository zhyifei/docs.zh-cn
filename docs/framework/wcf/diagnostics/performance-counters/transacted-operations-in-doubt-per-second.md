---
title: "Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e911a6112901ee92cb60adb4d2a7b028218d722d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="9f425-102">Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="9f425-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="9f425-103">计数器名称：Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="9f425-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="9f425-104">描述</span><span class="sxs-lookup"><span data-stu-id="9f425-104">Description</span></span>  
 <span data-ttu-id="9f425-105">此服务中每秒产生不确定结果的事务性操作的数量。</span><span class="sxs-lookup"><span data-stu-id="9f425-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="9f425-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="9f425-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="9f425-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="9f425-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
