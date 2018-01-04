---
title: "每秒拒绝的排队消息数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b413c5076e41990a794b9aa33efd371480835353
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="eae32-102">每秒拒绝的排队消息数</span><span class="sxs-lookup"><span data-stu-id="eae32-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="eae32-103">计数器名称：Queued Messages Rejected Per Second（每秒拒绝的排队消息数）。</span><span class="sxs-lookup"><span data-stu-id="eae32-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="eae32-104">描述</span><span class="sxs-lookup"><span data-stu-id="eae32-104">Description</span></span>  
 <span data-ttu-id="eae32-105">此服务中每秒被排队传输拒绝的消息数。</span><span class="sxs-lookup"><span data-stu-id="eae32-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="eae32-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="eae32-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="eae32-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="eae32-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
