---
title: 配置客户端行为
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 83fdc77bd17115f9952f2ca6c494ed0eb873cd9c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608770"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="723ab-102">配置客户端行为</span><span class="sxs-lookup"><span data-stu-id="723ab-102">Configuring Client Behaviors</span></span>
<span data-ttu-id="723ab-103">Windows Communication Foundation (WCF) 将行为配置两种方式： 通过引用中定义的行为配置，`<behavior>`部分中的客户端应用程序配置文件 – 或以编程方式调用中应用程序。</span><span class="sxs-lookup"><span data-stu-id="723ab-103">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="723ab-104">本主题将介绍这两种方式。</span><span class="sxs-lookup"><span data-stu-id="723ab-104">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="723ab-105">在使用配置文件时，行为配置为配置设置的命名集合。</span><span class="sxs-lookup"><span data-stu-id="723ab-105">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="723ab-106">每个行为配置的名称都必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="723ab-106">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="723ab-107">在终结点配置的 `behaviorConfiguration` 属性中，此字符串用来将终结点链接到该行为。</span><span class="sxs-lookup"><span data-stu-id="723ab-107">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="723ab-108">示例</span><span class="sxs-lookup"><span data-stu-id="723ab-108">Example</span></span>  
 <span data-ttu-id="723ab-109">下面的配置代码定义了一个称为 `myBehavior` 的行为。</span><span class="sxs-lookup"><span data-stu-id="723ab-109">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="723ab-110">客户端终结点在 `behaviorConfiguration` 属性中引用该行为。</span><span class="sxs-lookup"><span data-stu-id="723ab-110">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="723ab-111">以编程方式使用行为</span><span class="sxs-lookup"><span data-stu-id="723ab-111">Using Behaviors Programmatically</span></span>  
 <span data-ttu-id="723ab-112">你还可以配置或以编程方式插入行为，通过定位相应`Behaviors`Windows Communication Foundation (WCF) 客户端对象上或在打开客户端之前在客户端通道工厂对象的属性。</span><span class="sxs-lookup"><span data-stu-id="723ab-112">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="723ab-113">示例</span><span class="sxs-lookup"><span data-stu-id="723ab-113">Example</span></span>  
 <span data-ttu-id="723ab-114">下面的代码示例演示如何在创建通道对象之前访问从 <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> 属性返回的 <xref:System.ServiceModel.Description.ServiceEndpoint> 上的 <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> 属性，从而以编程方式插入行为。</span><span class="sxs-lookup"><span data-stu-id="723ab-114">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="723ab-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="723ab-115">See also</span></span>

- [<span data-ttu-id="723ab-116">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="723ab-116">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
