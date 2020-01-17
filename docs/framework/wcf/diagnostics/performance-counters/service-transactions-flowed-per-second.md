---
title: 服务：Transactions Flowed Per Second（每秒流动的事务数）
ms.date: 03/30/2017
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
ms.openlocfilehash: e8fbc314321a46fd3539998bd3dd22770086ca37
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164003"
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="817be-102">服务：Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="817be-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="817be-103">计数器名称：Transactions Flowed Per Second（每秒流动的事务数）。</span><span class="sxs-lookup"><span data-stu-id="817be-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="817be-104">描述</span><span class="sxs-lookup"><span data-stu-id="817be-104">Description</span></span>  
 <span data-ttu-id="817be-105">一秒内流向此服务中操作的事务数。</span><span class="sxs-lookup"><span data-stu-id="817be-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="817be-106">此计数器的性能计数器类型[PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10))，其值使用以下公式进行计算。</span><span class="sxs-lookup"><span data-stu-id="817be-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc740048(v=ws.10)), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="817be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="817be-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
