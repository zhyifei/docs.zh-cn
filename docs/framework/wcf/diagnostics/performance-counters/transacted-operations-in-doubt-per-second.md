---
title: Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: e165e934f17d599a9bb89f2702bb74d1ba0bf633
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474306"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="747d9-102">Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="747d9-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="747d9-103">计数器名称：Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="747d9-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="747d9-104">描述</span><span class="sxs-lookup"><span data-stu-id="747d9-104">Description</span></span>  
 <span data-ttu-id="747d9-105">此服务中每秒产生不确定结果的事务性操作的数量。</span><span class="sxs-lookup"><span data-stu-id="747d9-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="747d9-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="747d9-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="747d9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="747d9-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
