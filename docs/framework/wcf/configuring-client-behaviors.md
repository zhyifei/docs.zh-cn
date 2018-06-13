---
title: 配置客户端行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 062e726b6f1d6831303e1cc0ae82a434daab860c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458102"
---
# <a name="configuring-client-behaviors"></a>配置客户端行为
Windows Communication Foundation (WCF) 两种方式配置行为： 一是通过引用的行为配置，在中定义`<behavior>`的客户端应用程序配置文件 – 或以编程方式调用中的部分应用程序。 本主题将介绍这两种方式。  
  
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
 也可以配置，或以编程方式插入行为，通过定位适当`Behaviors`或之前打开客户端的客户端通道工厂对象上的 Windows Communication Foundation (WCF) 客户端对象的属性。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何在创建通道对象之前访问从 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 属性返回的 <xref:System.ServiceModel.Description.ServiceEndpoint> 上的 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 属性，从而以编程方式插入行为。  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>请参阅  
 [\<行为 >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
