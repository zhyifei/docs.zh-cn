---
title: "Calls Per Second（每秒调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0efb5a94-d83b-4793-b529-6fcbedb65c43
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 002c1aeb2f81c242adee5174340ea638ed85287f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="calls-per-second"></a><span data-ttu-id="1af1d-102">Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="1af1d-102">Calls Per Second</span></span>
<span data-ttu-id="1af1d-103">计数器名称：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="1af1d-103">Counter Name: Calls Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="1af1d-104">描述</span><span class="sxs-lookup"><span data-stu-id="1af1d-104">Description</span></span>  
 <span data-ttu-id="1af1d-105">一秒内对此操作调用的次数。</span><span class="sxs-lookup"><span data-stu-id="1af1d-105">Number of calls to this operation in a second.</span></span>  
  
 <span data-ttu-id="1af1d-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="1af1d-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="1af1d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="1af1d-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
