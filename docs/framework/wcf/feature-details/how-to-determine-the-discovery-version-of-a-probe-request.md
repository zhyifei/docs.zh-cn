---
title: "如何：确定探测请求的发现版本"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f51f48d6eefcc0f8ae5129526477d6e2a5b2385
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="c4b54-102">如何：确定探测请求的发现版本</span><span class="sxs-lookup"><span data-stu-id="c4b54-102">How to:Determine the Discovery Version of a Probe Request</span></span>
<span data-ttu-id="c4b54-103">发现代理可能会公开使用不同发现版本的多个发现终结点。</span><span class="sxs-lookup"><span data-stu-id="c4b54-103">A discovery proxy may expose multiple discovery endpoints using different discovery versions.</span></span> <span data-ttu-id="c4b54-104">当 UDP 多播探测请求到达代理时，代理应响应一条多播禁止消息。</span><span class="sxs-lookup"><span data-stu-id="c4b54-104">When a UDP multicast Probe request arrives at the proxy the proxy should respond with a multicast suppression message.</span></span> <span data-ttu-id="c4b54-105">为此，它必须知道请求的发现版本。</span><span class="sxs-lookup"><span data-stu-id="c4b54-105">In order to do this it would have to know the discovery version of the request.</span></span>  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a><span data-ttu-id="c4b54-106">确定探测请求的发现版本</span><span class="sxs-lookup"><span data-stu-id="c4b54-106">To Determine the Discovery Version of a Probe Request</span></span>  
  
1.  <span data-ttu-id="c4b54-107">在响应探测请求的方法（例如 <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>）中，使用静态 <xref:System.ServiceModel.OperationContext.Current%2A> 属性搜索  <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="c4b54-107">In the method that responds to a Probe request (for example <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>) use the static <xref:System.ServiceModel.OperationContext.Current%2A> property to search for a <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension> as shown in the following code.</span></span>  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c4b54-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b54-108">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [<span data-ttu-id="c4b54-109">实现发现代理</span><span class="sxs-lookup"><span data-stu-id="c4b54-109">Implementing a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [<span data-ttu-id="c4b54-110">发现代理示例</span><span class="sxs-lookup"><span data-stu-id="c4b54-110">Discovery Proxy Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
