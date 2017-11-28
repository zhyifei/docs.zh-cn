---
title: "Calls Failed Per Second（每秒失败的调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4ef3773-f650-4876-99cf-4d0c02aa03d4
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 504470a7338a22d058f6ae1f99192e9665b4d968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="calls-failed-per-second"></a><span data-ttu-id="981f4-102">Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="981f4-102">Calls Failed Per Second</span></span>
<span data-ttu-id="981f4-103">计数器名称：Calls Failed Per Second（每秒失败的调用次数）</span><span class="sxs-lookup"><span data-stu-id="981f4-103">Counter Name: Calls Failed Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="981f4-104">描述</span><span class="sxs-lookup"><span data-stu-id="981f4-104">Description</span></span>  
 <span data-ttu-id="981f4-105">该操作中每秒钟出现未处理异常的调用数目。</span><span class="sxs-lookup"><span data-stu-id="981f4-105">Number of calls with unhandled exceptions in this operation in a second.</span></span>  
  
 <span data-ttu-id="981f4-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="981f4-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="981f4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="981f4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="981f4-108">该操作中每出现一个未处理的异常，此计数器就会增加。</span><span class="sxs-lookup"><span data-stu-id="981f4-108">This counter is incremented everytime there is an unhandled exception in this operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981f4-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="981f4-109">See Also</span></span>  
 [<span data-ttu-id="981f4-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="981f4-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
