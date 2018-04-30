---
title: 通过 Discovery 客户端通道使用自定义绑定
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36f95e75-04f7-44f3-a995-a0d623624d7f
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a5c80a257efb5f6006a0cf6394a1079cf92d2471
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a><span data-ttu-id="05ccb-102">通过 Discovery 客户端通道使用自定义绑定</span><span class="sxs-lookup"><span data-stu-id="05ccb-102">Using a Custom Binding with the Discovery Client Channel</span></span>
<span data-ttu-id="05ccb-103">通过 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 使用自定义绑定时，必须定义创建 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 实例的 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>。</span><span class="sxs-lookup"><span data-stu-id="05ccb-103">When using a custom binding with the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, you must define a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> that creates <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances.</span></span>  
  
## <a name="creating-a-discoveryendpointprovider"></a><span data-ttu-id="05ccb-104">创建 DiscoveryEndpointProvider</span><span class="sxs-lookup"><span data-stu-id="05ccb-104">Creating a DiscoveryEndpointProvider</span></span>  
 <span data-ttu-id="05ccb-105"><xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>负责创建<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>按需的实例。</span><span class="sxs-lookup"><span data-stu-id="05ccb-105">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> is responsible for creating <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instances on demand.</span></span> <span data-ttu-id="05ccb-106">若要定义发现终结点提供程序，请从 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 派生类，然后覆盖 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> 方法并返回新发现终结点。</span><span class="sxs-lookup"><span data-stu-id="05ccb-106">To define a discovery endpoint provider, derive a class from <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> and override the <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> method and return a new discovery endpoint.</span></span> <span data-ttu-id="05ccb-107">下面的示例演示如何创建发现终结点提供程序。</span><span class="sxs-lookup"><span data-stu-id="05ccb-107">The following example shows how to create a discovery endpoint provider.</span></span>  
  
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
  
 <span data-ttu-id="05ccb-108">一旦定义了发现终结点提供程序，即可创建自定义绑定并添加引用发现终结点提供程序的 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="05ccb-108">Once you have defined the discovery endpoint provider you can create a custom binding and add the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>, which references the discovery endpoint provider as shown in the following example.</span></span>  
  
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
  
 <span data-ttu-id="05ccb-109">有关使用 discovery 客户端通道的详细信息，请参阅[使用 Discovery 客户端通道](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)。</span><span class="sxs-lookup"><span data-stu-id="05ccb-109">For more information about using the discovery client channel, see [Using the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md).</span></span> <span data-ttu-id="05ccb-110">有关完整的代码示例，请参阅[发现绑定元素示例](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)</span><span class="sxs-lookup"><span data-stu-id="05ccb-110">For a complete code example, see [Discovery Binding Element Sample](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05ccb-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="05ccb-111">See Also</span></span>  
 [<span data-ttu-id="05ccb-112">WCF 发现概述</span><span class="sxs-lookup"><span data-stu-id="05ccb-112">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="05ccb-113">使用发现客户端通道</span><span class="sxs-lookup"><span data-stu-id="05ccb-113">Using the Discovery Client Channel</span></span>](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [<span data-ttu-id="05ccb-114">发现绑定元素示例</span><span class="sxs-lookup"><span data-stu-id="05ccb-114">Discovery Binding Element Sample</span></span>](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
