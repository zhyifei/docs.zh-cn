---
title: "Transactions Flowed Per Second（每秒流动的事务数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9f661e1-576c-48fc-9fdf-91853e0749e8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed6adbaa1f121f11680e0f9574a642565a6f7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="transactions-flowed-per-second"></a><span data-ttu-id="5e2d9-102">Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="5e2d9-102">Transactions Flowed Per Second</span></span>
<span data-ttu-id="5e2d9-103">计数器名称：Transactions Flowed Per Second（每秒流动的事务数）</span><span class="sxs-lookup"><span data-stu-id="5e2d9-103">Counter Name:  Transactions Flowed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="5e2d9-104">描述</span><span class="sxs-lookup"><span data-stu-id="5e2d9-104">Description</span></span>  
 <span data-ttu-id="5e2d9-105">一秒内向此操作流动的事务数量。</span><span class="sxs-lookup"><span data-stu-id="5e2d9-105">Number of transactions flowed to this operation in a second.</span></span> <span data-ttu-id="5e2d9-106">每当发送到此操作的消息中存在事务 ID 时，此计数器就会增加。</span><span class="sxs-lookup"><span data-stu-id="5e2d9-106">This counter is incremented any time a transaction ID is present in a message that is sent to the operation.</span></span>  
  
 <span data-ttu-id="5e2d9-107">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="5e2d9-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5e2d9-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5e2d9-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
