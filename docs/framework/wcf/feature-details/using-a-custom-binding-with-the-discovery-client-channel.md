---
title: "通过 Discovery 客户端通道使用自定义绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 716dc09d38c778c49a1e2e5fa094ef1bf004eb46
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="75211-102">通过 Discovery 客户端通道使用自定义绑定</span><span class="sxs-lookup"><span data-stu-id="75211-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="75211-103">通过 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 使用自定义绑定时，必须定义创建 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 实例的 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>。</span><span class="sxs-lookup"><span data-stu-id="75211-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="75211-104">创建 DiscoveryEndpointProvider</span><span class="sxs-lookup"><span data-stu-id="75211-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="75211-105"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>负责创建<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>按需的实例。</span><span class="sxs-lookup"><span data-stu-id="75211-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="75211-106">若要定义发现终结点提供程序，请从 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 派生类，然后覆盖 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> 方法并返回新发现终结点。</span><span class="sxs-lookup"><span data-stu-id="75211-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="75211-107">下面的示例演示如何创建发现终结点提供程序。</span><span class="sxs-lookup"><span data-stu-id="75211-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
// to the DiscoveryClientBindingElement. The Discovery ClientChannel   
// uses this endpoint to send Probe message.  
public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
{  
   public override DiscoveryEndpoint GetDiscoveryEndpoint()  
   {  
      return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
   }  
}  
```  
  
 <span data-ttu-id="75211-108">一旦定义了发现终结点提供程序，即可创建自定义绑定并添加引用发现终结点提供程序的 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="75211-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
```  
DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
// Provide the search criteria and the endpoint over which the probe is sent.  
discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
// Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
// An exception is thrown if this binding element is not at the top.  
customBinding.Elements.Insert(0, discoveryBindingElement);  
```  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="75211-109">使用 discovery 客户端通道，请参阅[使用 Discovery 客户端通道](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)。</span><span class="sxs-lookup"><span data-stu-id="75211-109"> using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span> <span data-ttu-id="75211-110">有关完整的代码示例，请参阅[发现绑定元素示例](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)</span><span class="sxs-lookup"><span data-stu-id="75211-110">For a complete code example, see [Discovery Binding Element Sample](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75211-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75211-111">See Also</span></span>  
 [<span data-ttu-id="75211-112">WCF Discovery 概述</span><span class="sxs-lookup"><span data-stu-id="75211-112">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="75211-113">使用 Discovery 客户端通道</span><span class="sxs-lookup"><span data-stu-id="75211-113">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [<span data-ttu-id="75211-114">发现绑定元素示例</span><span class="sxs-lookup"><span data-stu-id="75211-114">Discovery Binding Element Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
