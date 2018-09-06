---
title: 终结点：Calls Faulted Per Second（每秒出错的调用次数）
ms.date: 03/30/2017
ms.assetid: 9840fc0a-0e4d-4638-96fd-40e3ab9e4667
ms.openlocfilehash: f1b2997a0f1e16c897fc319d1833313141f5c4bf
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43874675"
---
# <a name="endpoint-calls-faulted-per-second"></a><span data-ttu-id="08b2c-102">终结点：Calls Faulted Per Second（每秒出错的调用次数）</span><span class="sxs-lookup"><span data-stu-id="08b2c-102">Endpoint: Calls Faulted Per Second</span></span>
<span data-ttu-id="08b2c-103">计数器名称：Calls Faulted Per Second（每秒出错的调用次数）。</span><span class="sxs-lookup"><span data-stu-id="08b2c-103">Counter Name: Calls Faulted Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="08b2c-104">描述</span><span class="sxs-lookup"><span data-stu-id="08b2c-104">Description</span></span>  
 <span data-ttu-id="08b2c-105">一秒内向此终结点返回了错误的调用的数目。</span><span class="sxs-lookup"><span data-stu-id="08b2c-105">Number of calls that have returned faults to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="08b2c-106">此计数器为性能计数器类型[PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649)，使用以下公式计算其值。</span><span class="sxs-lookup"><span data-stu-id="08b2c-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="08b2c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="08b2c-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>  
  
 <span data-ttu-id="08b2c-108">在 Windows Communication Foundation (WCF) 应用程序中服务方法进行通信使用 SOAP 错误消息的处理错误信息。</span><span class="sxs-lookup"><span data-stu-id="08b2c-108">In Windows Communication Foundation (WCF) applications, service methods communicate processing error information using SOAP fault messages.</span></span> <span data-ttu-id="08b2c-109">SOAP 错误是包括在服务操作元数据中的消息类型，因此会创建一个错误协定，客户端可使用该协定来使执行更加可靠或更具交互性。</span><span class="sxs-lookup"><span data-stu-id="08b2c-109">SOAP faults are message types that are included in the metadata for a service operation and therefore create a fault contract that clients can use to make their execution more robust or interactive.</span></span> <span data-ttu-id="08b2c-110">由于 SOAP 错误在客户端以 XML 格式表示，因此具有高度的互操作性。</span><span class="sxs-lookup"><span data-stu-id="08b2c-110">Since SOAP faults are expressed to clients in XML form, they are highly interoperable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b2c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="08b2c-111">See Also</span></span>  
 [<span data-ttu-id="08b2c-112">在协定和服务中指定并处理错误</span><span class="sxs-lookup"><span data-stu-id="08b2c-112">Specifying and Handling Faults in Contracts and Services</span></span>](../../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
