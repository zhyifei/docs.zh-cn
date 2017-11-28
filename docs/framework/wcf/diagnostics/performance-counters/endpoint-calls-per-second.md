---
title: "终结点：Calls Per Second（每秒调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 559bc945cde67a89d7e0fcdcde3f50e8ff51a138
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="b9ade-102">终结点：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="b9ade-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="b9ade-103">计数器名称：Calls Per Second（每秒调用次数）</span><span class="sxs-lookup"><span data-stu-id="b9ade-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="b9ade-104">描述</span><span class="sxs-lookup"><span data-stu-id="b9ade-104">Description</span></span>  
 <span data-ttu-id="b9ade-105">一秒内对此终结点的调用次数。</span><span class="sxs-lookup"><span data-stu-id="b9ade-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="b9ade-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="b9ade-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="b9ade-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="b9ade-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
