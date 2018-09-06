---
title: Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
ms.openlocfilehash: 124eae3b36a731ac50a147782b19c87e3adfa7be
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856317"
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="15ae3-102">Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="15ae3-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="15ae3-103">计数器名称：Transacted Operations Committed Per Second（每秒提交的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="15ae3-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="15ae3-104">描述</span><span class="sxs-lookup"><span data-stu-id="15ae3-104">Description</span></span>  
 <span data-ttu-id="15ae3-105">此服务中每秒提交的事务处理操作的数量。</span><span class="sxs-lookup"><span data-stu-id="15ae3-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="15ae3-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="15ae3-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="15ae3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="15ae3-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
