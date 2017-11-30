---
title: "服务：Calls Faulted（出错的调用次数）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f82558bdacbc36569329764aa1639c81146d9127
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="service-calls-faulted"></a><span data-ttu-id="69d58-102">服务：Calls Faulted（出错的调用次数）</span><span class="sxs-lookup"><span data-stu-id="69d58-102">Service: Calls Faulted</span></span>
<span data-ttu-id="69d58-103">计数器名称：Calls Faulted（出错的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="69d58-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="69d58-104">描述</span><span class="sxs-lookup"><span data-stu-id="69d58-104">Description</span></span>  
 <span data-ttu-id="69d58-105">此服务的返回错误的调用次数。</span><span class="sxs-lookup"><span data-stu-id="69d58-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="69d58-106">在 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 应用程序中，服务方法使用 SOAP 错误消息来传递处理错误信息。</span><span class="sxs-lookup"><span data-stu-id="69d58-106">In [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="69d58-107">SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。</span><span class="sxs-lookup"><span data-stu-id="69d58-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="69d58-108">由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。</span><span class="sxs-lookup"><span data-stu-id="69d58-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d58-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69d58-109">See Also</span></span>  
 [<span data-ttu-id="69d58-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="69d58-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
