---
title: "服务：Calls Failed Per Second（每秒失败的调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a2c7939-107d-4f0c-b43c-e02e079e8a9d
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2072a686d5d424f90ac2f32cf5fc11564b07542c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-failed-per-second"></a><span data-ttu-id="ba8e8-102">服务：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="ba8e8-102">Service: Calls Failed Per Second</span></span>
<span data-ttu-id="ba8e8-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="ba8e8-103">Counter Name: Calls Failed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="ba8e8-104">描述</span><span class="sxs-lookup"><span data-stu-id="ba8e8-104">Description</span></span>  
 <span data-ttu-id="ba8e8-105">一秒钟内由此服务收到且具有未处理异常的调用次数。</span><span class="sxs-lookup"><span data-stu-id="ba8e8-105">Number of calls that have unhandled exceptions, and are received by this service in a second.</span></span>  
  
 <span data-ttu-id="ba8e8-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="ba8e8-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ba8e8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ba8e8-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="ba8e8-108">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="ba8e8-108">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="ba8e8-109">在托管代码中，出现错误条件时引发异常。</span><span class="sxs-lookup"><span data-stu-id="ba8e8-109">In managed code, exceptions are thrown when error conditions occur.</span></span>  
  
 <span data-ttu-id="ba8e8-110">此服务中每出现一个未处理异常，此计数器就会递增。</span><span class="sxs-lookup"><span data-stu-id="ba8e8-110">This counter is incremented every time there is an unhandled exception in this service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8e8-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba8e8-111">See Also</span></span>  
 [<span data-ttu-id="ba8e8-112">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="ba8e8-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
