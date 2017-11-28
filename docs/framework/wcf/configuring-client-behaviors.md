---
title: "配置客户端行为"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f16f32128c7223fa600802ae593d36286847dc8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="configuring-client-behaviors"></a>配置客户端行为
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 通过两种方式配置行为：一是通过引用在客户端应用程序配置文件的 `<behavior>` 节中定义的行为配置，二是在调用应用程序中采用编程方式进行配置。 本主题将介绍这两种方式。  
  
 在使用配置文件时，行为配置为配置设置的命名集合。 每个行为配置的名称都必须是唯一的。 在终结点配置的 `behaviorConfiguration` 属性中，此字符串用来将终结点链接到该行为。  
  
## <a name="example"></a>示例  
 下面的配置代码定义了一个称为 `myBehavior` 的行为。 客户端终结点在 `behaviorConfiguration` 属性中引用该行为。  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a>以编程方式使用行为  
 也可以通过编程方式配置或插入行为，方法是在打开客户端之前查找 `Behaviors` 客户端对象或客户端通道工厂对象上的相应 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 属性。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何在创建通道对象之前访问从 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 属性返回的 <xref:System.ServiceModel.Description.ServiceEndpoint> 上的 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 属性，从而以编程方式插入行为。  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>另请参阅  
 [\<行为 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
