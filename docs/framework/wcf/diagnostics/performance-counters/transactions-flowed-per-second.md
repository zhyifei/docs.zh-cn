---
title: Transactions Flowed Per Second（每秒流动的事务数）
ms.date: 03/30/2017
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
ms.openlocfilehash: a71095b9fdd16d7e220be8a0aeb0a746bb50527e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33472913"
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="341f4-102">Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="341f4-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="341f4-103">计数器名称：Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="341f4-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="341f4-104">描述</span><span class="sxs-lookup"><span data-stu-id="341f4-104">Description</span></span>  
 <span data-ttu-id="341f4-105">一秒内向此操作流动的事务数量。</span><span class="sxs-lookup"><span data-stu-id="341f4-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="341f4-106">每当发送到此操作的消息中存在事务 ID 时，此计数器就会增加。</span><span class="sxs-lookup"><span data-stu-id="341f4-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="341f4-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="341f4-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="341f4-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="341f4-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
