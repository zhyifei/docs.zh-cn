---
title: 客户端配置
ms.date: 03/30/2017
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
ms.openlocfilehash: 6a5cbf5d536af8649b0b8bb93600e94a48c507c1
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141768"
---
# <a name="client-configuration"></a>客户端配置
您可以使用 Windows Communication Foundation （WCF）客户端配置来指定客户端终结点的地址、绑定、行为和协定，客户端终结点的 "ABC" 属性用于连接到服务终结点。 [\<客户端 >](../../configure-apps/file-schema/wcf/client.md)元素具有一个[\<终结点 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md)元素，其属性用于配置终结点 abc。 这些属性在[配置终结点](#configuring-endpoints)部分中进行了讨论。  
  
 [\<终结点 >](../../configure-apps/file-schema/wcf/endpoint-of-client.md)元素还包含一个[\<元数据 >](../../configure-apps/file-schema/wcf/metadata.md)元素，该元素用于指定导入和导出元数据的设置、一个包含自定义地址标头集合的[\<标头 >](../../configure-apps/file-schema/wcf/headers.md)元素，以及一个[\<标识 >](../../configure-apps/file-schema/wcf/identity.md)元素，通过该元素，可通过与该终结点交换消息的其他终结点对该终结点进行身份验证。 [\<标头 >](../../configure-apps/file-schema/wcf/headers.md)和[\<标识 >](../../configure-apps/file-schema/wcf/identity.md)元素是 <xref:System.ServiceModel.EndpointAddress> 的一部分，并在 "[地址](../../wcf/feature-details/endpoint-addresses.md)" 一文中进行讨论。 在[配置元数据](#configuring-metadata)部分中提供了指向说明元数据扩展使用的主题的链接。  
  
## <a name="configuring-endpoints"></a>配置终结点  
 客户端配置旨在允许客户端指定一个或多个终结点，每个终结点都有自己的名称、地址和协定，每个终结点都引用[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)并[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)要用于配置该终结点的客户端配置中的元素。 应将客户端配置文件命名为 "App.config"，因为这是 WCF 运行时需要的名称。 下面的示例演示一个客户端配置文件。  
  
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
// Add another endpoint by adding another <endpoint> element.  
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
        //Configure this binding here.  
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
  
 可选的 `name` 属性唯一地标识了给定协定的终结点。 它由 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 或 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> 用于指定客户端配置中的哪个终结点是目标终结点，必须在创建到服务的通道时加载。 通配符终结点配置名称 "\*" 可用，并向 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 方法指示它应将任何终结点配置加载到文件中（只要有精确可用），否则会引发异常。 如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。 `name` 属性的默认值是一个空字符串，它与任何其他名称一样进行匹配。  
  
 每个终结点都必须具有一个与之关联的地址，用于查找和标识终结点。 `address` 属性可用来指定提供终结点位置的 URL。 但是，通过创建统一资源标识符 (URI)，也可以在代码中指定服务终结点的地址，使用 <xref:System.ServiceModel.ServiceHost> 方法之一可以将该地址添加到 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>。 有关详细信息，请参阅[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)。 正如简介中所述， [\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)和[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素都是 <xref:System.ServiceModel.EndpointAddress> 的一部分，并且还会在 "[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)" 主题中讨论。  
  
 `binding` 属性指示终结点在连接到服务时期望使用的绑定类型。 该类型必须具有一个已注册的配置节，才能加以引用。 在前面的示例中，这是[\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)部分，指示终结点使用 <xref:System.ServiceModel.WSHttpBinding>。 实际上，终结点可以使用某个给定类型的多个绑定。 其中每个元素都有其自己的[\<绑定](../../configure-apps/file-schema/wcf/bindings.md)（绑定）类型元素中的 > 元素。 `bindingconfiguration` 属性用于区分相同类型的绑定。 它的值与[\<绑定 >](../../configure-apps/file-schema/wcf/bindings.md)元素的 `name` 特性相匹配。 有关如何使用配置来配置客户端绑定的详细信息，请参阅[如何：在配置中指定客户端绑定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)。  
  
 `behaviorConfiguration` 特性用于指定终结点应使用的[\<> endpointBehaviors](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)的[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) 。 它的值与 > 元素的[\<行为](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)的 `name` 特性相匹配。 有关使用配置来指定客户端行为的示例，请参阅[配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)。  
  
 `contract` 属性指定终结点公开哪个协定。 此值对应于 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> 的 <xref:System.ServiceModel.ServiceContractAttribute>。 默认值为实现相应服务的类的完整类型名。  
  
### <a name="configuring-metadata"></a>配置元数据  
 [\<metadata >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)元素用于指定用于注册元数据导入扩展的设置。 有关扩展元数据系统的详细信息，请参阅[扩展元数据系统](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)。  
  
## <a name="see-also"></a>请参阅

- [终结点：地址、绑定和协定](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
- [配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)
