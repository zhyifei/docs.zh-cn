---
title: 服务：Calls Faulted（出错的调用次数）
ms.date: 03/30/2017
ms.assetid: 6da7f100-3f61-4b3c-9409-fe1360829b8a
ms.openlocfilehash: f50a2a0bf594d93fea2678b6be26f5d8a16f6b63
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688592"
---
# <a name="service-calls-faulted"></a><span data-ttu-id="50b0c-102">服务：Calls Faulted（出错的调用次数）</span><span class="sxs-lookup"><span data-stu-id="50b0c-102">Service: Calls Faulted</span></span>
<span data-ttu-id="50b0c-103">计数器名称：出错的调用。</span><span class="sxs-lookup"><span data-stu-id="50b0c-103">Counter Name: Calls Faulted.</span></span>  
  
## <a name="description"></a><span data-ttu-id="50b0c-104">描述</span><span class="sxs-lookup"><span data-stu-id="50b0c-104">Description</span></span>  
 <span data-ttu-id="50b0c-105">此服务的返回错误的调用次数。</span><span class="sxs-lookup"><span data-stu-id="50b0c-105">Number of calls to this service that have returned faults.</span></span> <span data-ttu-id="50b0c-106">在 Windows Communication Foundation (WCF) 应用程序中服务方法进行通信使用 SOAP 错误消息的处理错误信息。</span><span class="sxs-lookup"><span data-stu-id="50b0c-106">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="50b0c-107">SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。</span><span class="sxs-lookup"><span data-stu-id="50b0c-107">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="50b0c-108">由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。</span><span class="sxs-lookup"><span data-stu-id="50b0c-108">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50b0c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="50b0c-109">See also</span></span>
- [<span data-ttu-id="50b0c-110">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="50b0c-110">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
