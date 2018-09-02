---
title: 终结点：Transactions Flowed Per Second（每秒流动的事务数）
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: 79f50b6706facd040ec2d325c676f210d5327bf8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43405006"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="64a60-102">终结点：Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="64a60-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="64a60-103">计数器名称：Transactions Flowed Per Second（每秒流动的事务数）。</span><span class="sxs-lookup"><span data-stu-id="64a60-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="64a60-104">描述</span><span class="sxs-lookup"><span data-stu-id="64a60-104">Description</span></span>  
 <span data-ttu-id="64a60-105">一秒内流向此终结点上的操作的事务数。</span><span class="sxs-lookup"><span data-stu-id="64a60-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="64a60-106">只要发送到终结点的消息中出现事务 ID，此计数器即会递增。</span><span class="sxs-lookup"><span data-stu-id="64a60-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="64a60-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="64a60-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="64a60-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="64a60-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
