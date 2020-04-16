---
title: 客户端配置
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 141b7f7fc04f98f267ce520544fb89451beac7b6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463867"
---
# <a name="client-configuration"></a>客户端配置
您可以使用 Windows 通信基础 （WCF） 客户端配置来指定客户端终结点的地址、绑定、行为和协定、客户端终结点的"ABC"属性，客户端用于连接到服务终结点。 客户端>元素具有[\<终结点>](../../configure-apps/file-schema/wcf/endpoint-of-client.md)元素，其属性用于配置终结点 ABC。 [ \<](../../configure-apps/file-schema/wcf/client.md) 这些属性在["配置终结点"](#configuring-endpoints)部分中讨论。  
  
 [\<终结点>](../../configure-apps/file-schema/wcf/endpoint-of-client.md)元素还包含用于指定导入和导出元数据的设置[\<的元数据>](../../configure-apps/file-schema/wcf/metadata.md)元素、[\<](../../configure-apps/file-schema/wcf/headers.md)包含自定义地址标头集合>标头以及允许通过与其他终结点交换消息的终结点进行终结点身份验证[\<的标识>](../../configure-apps/file-schema/wcf/identity.md)元素。 >[和\<标识>](../../configure-apps/file-schema/wcf/identity.md)元素[\<的标头](../../configure-apps/file-schema/wcf/headers.md)是 中的一部分<xref:System.ServiceModel.EndpointAddress>，并在["地址"](../../wcf/feature-details/endpoint-addresses.md)一文中讨论。 "[配置元数据](#configuring-metadata)"部分提供了指向解释元数据扩展使用的主题的链接。  
  
## <a name="configuring-endpoints"></a>配置终结点  
 客户端配置旨在允许客户端指定一个或多个终结点，每个终结点都有自己的名称、地址和协定，每个终结点引用[\<绑定>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)[\<和行为>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)客户端配置中用于配置该终结点的元素。 客户端配置文件应命名为"App.config"，因为这是 WCF 运行时期望的名称。 下面的示例演示一个客户端配置文件。  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
        <client>  
          <endpoint  
            name="endpoint1"  
            address="http://localhost/ServiceModelSamples/service.svc"  
            binding="wsHttpBinding"  
            bindingConfiguration="WSHttpBinding_IHello"  
            behaviorConfiguration="IHello_Behavior"  
            contract="IHello" >  
  
            <metadata>  
              <wsdlImporters>  
                <extension  
                  type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
              </wsdlImporters>  
            </metadata>  
  
            <identity>  
              <servicePrincipalName value="host/localhost" />  
            </identity>  
          </endpoint>  
            <!-- Add another endpoint by adding another <endpoint> element. -->
          <endpoint  
            name="endpoint2">  
           //Configure another endpoint here.  
          </endpoint>  
        </client>  
  
//The bindings section references by the bindingConfiguration endpoint attribute.  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_IHello"
                 bypassProxyOnLocal="false"
                 hostNameComparisonMode="StrongWildcard">  
          <readerQuotas maxDepth="32"/>  
          <reliableSession ordered="true"
                           enabled="false" />  
          <security mode="Message">  
           //Security settings go here.  
          </security>  
        </binding>  
        <binding name="Another Binding"  
          <!-- Configure this binding here. -->  
        </binding>  
          </wsHttpBinding>  
     </bindings>  
  
//The behavior section references by the behaviorConfiguration endpoint attribute.  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name=" IHello_Behavior ">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
  
    </system.serviceModel>  
</configuration>  
```  
  
 可选的 `name` 属性唯一地标识了给定协定的终结点。 它由 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 或 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> 用于指定客户端配置中的哪个终结点是目标终结点，必须在创建到服务的通道时加载。 通配符终结点配置名称""\*可用，并指示<xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A>方法应加载文件中的任何终结点配置，前提是正好有一个可用，否则将引发异常。 如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。 `name` 属性的默认值是一个空字符串，它与任何其他名称一样进行匹配。  
  
 每个终结点都必须具有一个与之关联的地址，用于查找和标识终结点。 `address` 属性可用来指定提供终结点位置的 URL。 但是，通过创建统一资源标识符 (URI)，也可以在代码中指定服务终结点的地址，使用 <xref:System.ServiceModel.ServiceHost> 方法之一可以将该地址添加到 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>。 有关详细信息，请参阅[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)。 如导言所示[\<，>和](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)[\<标识>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素的标头是 中的一<xref:System.ServiceModel.EndpointAddress>部分，在["地址"](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)主题中也进行了讨论。  
  
 `binding` 属性指示终结点在连接到服务时期望使用的绑定类型。 该类型必须具有一个已注册的配置节，才能加以引用。 在前面的示例中，这是[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)部分，指示终结点使用<xref:System.ServiceModel.WSHttpBinding>。 实际上，终结点可以使用某个给定类型的多个绑定。 其中每个元素在（绑定）类型元素中都有自己的[\<绑定>](../../configure-apps/file-schema/wcf/bindings.md)元素。 `bindingconfiguration` 属性用于区分相同类型的绑定。 其值与[\<绑定>](../../configure-apps/file-schema/wcf/bindings.md)元素`name`的属性匹配。 有关如何使用配置配置客户端绑定的详细信息，请参阅[如何：在 配置 中指定客户端绑定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)。  
  
 该`behaviorConfiguration`属性用于指定[\<终结点](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)行为[\<>哪些行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)>终结点应使用。 其值与[\<行为>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)元素`name`的属性匹配。 有关使用配置指定客户端行为的示例，请参阅[配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)。  
  
 `contract` 属性指定终结点公开哪个协定。 此值对应于 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> 的 <xref:System.ServiceModel.ServiceContractAttribute>。 默认值为实现相应服务的类的完整类型名。  
  
### <a name="configuring-metadata"></a>配置元数据  
 元数据>元素用于指定用于注册元数据导入扩展的设置。 [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md) 有关扩展元数据系统的详细信息，请参阅[扩展元数据系统](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)。  
  
## <a name="see-also"></a>请参阅

- [终结点：地址、绑定和协定](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)
