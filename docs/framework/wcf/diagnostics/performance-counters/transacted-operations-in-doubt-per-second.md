---
title: Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: bc978f5b45352fa9fcce5aee5a616c9f86f56aeb
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163834"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="b4ad2-102">Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）</span><span class="sxs-lookup"><span data-stu-id="b4ad2-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="b4ad2-103">计数器名称：Transacted Operations In Doubt Per Second（每秒不确定的事务处理操作次数）。</span><span class="sxs-lookup"><span data-stu-id="b4ad2-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4ad2-104">描述</span><span class="sxs-lookup"><span data-stu-id="b4ad2-104">Description</span></span>  
 <span data-ttu-id="b4ad2-105">此服务中每秒产生不确定结果的事务性操作的数量。</span><span class="sxs-lookup"><span data-stu-id="b4ad2-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="b4ad2-106">此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="b4ad2-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b4ad2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b4ad2-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
