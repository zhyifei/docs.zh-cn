---
title: 服务：Calls Faulted（出错的调用次数）
ms.date: 03/30/2017
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
ms.openlocfilehash: 233033eb32654b96efa6ddaa21991047d66873cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090675"
---
# <a name="service-calls-faulted"></a><span data-ttu-id="95d4f-102">服务：Calls Faulted（出错的调用次数）</span><span class="sxs-lookup"><span data-stu-id="95d4f-102">Service: Calls Faulted</span></span>
<span data-ttu-id="95d4f-103">计数器名称：出错的调用。</span><span class="sxs-lookup"><span data-stu-id="95d4f-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="95d4f-104">描述</span><span class="sxs-lookup"><span data-stu-id="95d4f-104">Description</span></span>  
 <span data-ttu-id="95d4f-105">此服务的返回错误的调用次数。</span><span class="sxs-lookup"><span data-stu-id="95d4f-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="95d4f-106">在 Windows Communication Foundation (WCF) 应用程序中服务方法进行通信使用 SOAP 错误消息的处理错误信息。</span><span class="sxs-lookup"><span data-stu-id="95d4f-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="95d4f-107">SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。</span><span class="sxs-lookup"><span data-stu-id="95d4f-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="95d4f-108">由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。</span><span class="sxs-lookup"><span data-stu-id="95d4f-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95d4f-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="95d4f-109">See also</span></span>

- [<span data-ttu-id="95d4f-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="95d4f-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
