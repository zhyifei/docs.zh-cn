---
title: "终结点：Calls Failed Per Second（每秒失败的调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bcbe9da4-c8dd-4e27-b630-11611adc7580
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b41a1fba1c1630532524bb4d6bc759ec21e2865
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="endpoint-calls-failed-per-second"></a><span data-ttu-id="75be1-102">终结点：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="75be1-102">Endpoint: Calls Failed Per Second</span></span>
<span data-ttu-id="75be1-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="75be1-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="75be1-104">描述</span><span class="sxs-lookup"><span data-stu-id="75be1-104">Description</span></span>  
 <span data-ttu-id="75be1-105">一秒钟内通过此终结点收到且具有未处理的异常的调用次数。</span><span class="sxs-lookup"><span data-stu-id="75be1-105">Number of calls that have unhandled exceptions and are received by this endpoint in a second.</span></span>  
  
 <span data-ttu-id="75be1-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="75be1-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="75be1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="75be1-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="75be1-108">每当此终结点处有未处理的异常时，此计数器就会增加。</span><span class="sxs-lookup"><span data-stu-id="75be1-108">This counter is incremented every time there is an unhandled exception at this endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75be1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75be1-109">See Also</span></span>  
 [<span data-ttu-id="75be1-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="75be1-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
