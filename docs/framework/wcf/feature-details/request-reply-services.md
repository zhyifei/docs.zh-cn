---
title: "请求-答复服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a38a90d4e9ec249f91e8bfda88c646c006890d8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="request-reply-services"></a><span data-ttu-id="f1ea6-102">请求-答复服务</span><span class="sxs-lookup"><span data-stu-id="f1ea6-102">Request-Reply Services</span></span>
<span data-ttu-id="f1ea6-103">请求-答复服务是 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中操作协定的默认类型。</span><span class="sxs-lookup"><span data-stu-id="f1ea6-103">Request-reply services are the default type of operation contract in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="f1ea6-104">客户端调用服务操作并等待服务的响应。</span><span class="sxs-lookup"><span data-stu-id="f1ea6-104">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="f1ea6-105">您可以同步执行对服务操作的调用（客户端接收到服务的响应或调用超时前客户端将保持阻止状态），也可以异步执行对服务操作的调用（客户端调用服务操作，继续工作，并在其他线程上接收服务的响应）。</span><span class="sxs-lookup"><span data-stu-id="f1ea6-105">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="f1ea6-106">若要创建请求-答复服务协定，请定义服务协定，然后对每个操作应用 <xref:System.ServiceModel.OperationContractAttribute> 类，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="f1ea6-106">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="f1ea6-107">您不必将 <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> 属性设置为 `false`，因为这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="f1ea6-107">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1ea6-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1ea6-108">See Also</span></span>  
 [<span data-ttu-id="f1ea6-109">单向服务</span><span class="sxs-lookup"><span data-stu-id="f1ea6-109">One-Way Services</span></span>](../../../../docs/framework/wcf/feature-details/one-way-services.md)  
 [<span data-ttu-id="f1ea6-110">双工服务</span><span class="sxs-lookup"><span data-stu-id="f1ea6-110">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)
