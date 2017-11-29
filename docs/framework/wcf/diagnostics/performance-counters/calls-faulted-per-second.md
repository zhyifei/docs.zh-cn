---
title: "Calls Faulted Per Second（每秒出错的调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81c88073-8e32-4520-a71a-2c56b71ee515
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e60ad3d7e9155eecfead38aca080a3044b0efce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="calls-faulted-per-second"></a><span data-ttu-id="ff3cf-102">Calls Faulted Per Second（每秒出错的调用次数）</span><span class="sxs-lookup"><span data-stu-id="ff3cf-102">Calls Faulted Per Second</span></span>
<span data-ttu-id="ff3cf-103">计数器名称：Calls Faulted Per Second（每秒出错的调用次数）</span><span class="sxs-lookup"><span data-stu-id="ff3cf-103">Counter Name: Calls Faulted Per Second</span></span>  
  
## <a name="description"></a><span data-ttu-id="ff3cf-104">描述</span><span class="sxs-lookup"><span data-stu-id="ff3cf-104">Description</span></span>  
 <span data-ttu-id="ff3cf-105">一秒内向此操作返回了错误的调用的数目。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-105">Number of calls that returned faults to this operation in a second.</span></span>  
  
 <span data-ttu-id="ff3cf-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="ff3cf-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="ff3cf-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="ff3cf-108">在 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 应用程序中，服务方法使用 SOAP 错误消息来传递处理错误信息。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-108">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="ff3cf-109">SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="ff3cf-110">由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。</span><span class="sxs-lookup"><span data-stu-id="ff3cf-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff3cf-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff3cf-111">See Also</span></span>  
 [<span data-ttu-id="ff3cf-112">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="ff3cf-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
