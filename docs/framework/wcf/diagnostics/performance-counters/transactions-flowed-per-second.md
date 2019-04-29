---
title: Transactions Flowed Per Second（每秒流动的事务数）
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: e77aef4cfff1e64f112e720183675dfb7aa25d27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61927187"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="2ec9d-102">Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="2ec9d-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="2ec9d-103">计数器名称：Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="2ec9d-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="2ec9d-104">描述</span><span class="sxs-lookup"><span data-stu-id="2ec9d-104">Description</span></span>  
 <span data-ttu-id="2ec9d-105">一秒内向此操作流动的事务数量。</span><span class="sxs-lookup"><span data-stu-id="2ec9d-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="2ec9d-106">每当发送到此操作的消息中存在事务 ID 时，此计数器就会增加。</span><span class="sxs-lookup"><span data-stu-id="2ec9d-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="2ec9d-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="2ec9d-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="2ec9d-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="2ec9d-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
