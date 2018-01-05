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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 85c88132b1fa610b2bcb63635ae553ef47bb359c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-custom-binding-with-the-discovery-client-channel"></a>通过 Discovery 客户端通道使用自定义绑定
通过 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> 使用自定义绑定时，必须定义创建 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 实例的 <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>。  
  
## <a name="creating-a-discoveryendpointprovider"></a>创建 DiscoveryEndpointProvider  
 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider>负责创建<xref:System.ServiceModel.Discovery.DiscoveryEndpoint>按需的实例。 若要定义发现终结点提供程序，请从 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> 派生类，然后覆盖 <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider.GetDiscoveryEndpoint%2A> 方法并返回新发现终结点。 下面的示例演示如何创建发现终结点提供程序。  
  
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
  
 一旦定义了发现终结点提供程序，即可创建自定义绑定并添加引用发现终结点提供程序的 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>，如下面的示例所示。  
  
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
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]使用 discovery 客户端通道，请参阅[使用 Discovery 客户端通道](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)。 有关完整的代码示例，请参阅[发现绑定元素示例](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)  
  
## <a name="see-also"></a>请参阅  
 [WCF 发现概述](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [使用发现客户端通道](../../../../docs/framework/wcf/feature-details/using-the-discovery-client-channel.md)  
 [发现绑定元素示例](../../../../docs/framework/wcf/samples/discovery-binding-element-sample.md)
