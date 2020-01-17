---
title: 终结点：Transactions Flowed Per Second（每秒流动的事务数）
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 39458dcb6ac033fd5084b5f2e760e0e26c345da7
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163548"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="ccef4-102">终结点：Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="ccef4-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="ccef4-103">计数器名称：Transactions Flowed Per Second（每秒流动的事务数）。</span><span class="sxs-lookup"><span data-stu-id="ccef4-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ccef4-104">描述</span><span class="sxs-lookup"><span data-stu-id="ccef4-104">Description</span></span>  
 <span data-ttu-id="ccef4-105">一秒内流向此终结点上的操作的事务数。</span><span class="sxs-lookup"><span data-stu-id="ccef4-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="ccef4-106">只要发送到终结点的消息中出现事务 ID，此计数器即会递增。</span><span class="sxs-lookup"><span data-stu-id="ccef4-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="ccef4-107">此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="ccef4-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ccef4-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ccef4-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
