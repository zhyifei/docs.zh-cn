---
title: "客户端配置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5da5bd3b-65d9-43b7-91b9-cc9e989b1350
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7ece2585287f6e2767e64c2ec03c75adcfe161c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="client-configuration"></a>客户端配置
可以使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端配置来指定客户端终结点的地址 (Address)、绑定 (Binding)、行为 (Behavior) 和协定 (Contract)，即客户端终结点的“ABC”属性来连接服务终结点。 [\<客户端 >](../../../../docs/framework/configure-apps/file-schema/wcf/client.md)元素具有[\<终结点 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)其属性用于配置终结点的 abc 属性的元素。 这些属性将在本主题的“配置终结点”一节中讨论。  
  
 [\<终结点 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素还包含[\<元数据 >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)元素，用于指定用于导入和导出元数据，设置[ \<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)包含自定义地址标头的集合的元素和[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)进行身份验证的其他终结点的终结点的元素交换与其消息。 [\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)和[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素属于<xref:System.ServiceModel.EndpointAddress>进行讨论[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)主题。 本主题的“配置元数据”子节中提供了一些主题链接，这些主题对元数据扩展的使用进行说明。  
  
## <a name="configuring-endpoints"></a>配置终结点  
 客户端配置旨在允许客户端指定一个或多个终结点，每个都有其自己的名称，地址、 和协定，与每个引用[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)和[ \<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)要用于配置该终结点的客户端配置中的元素。 客户端配置文件应命名为“App.config”，因为这是 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 运行库所期望的名称。 下面的示例演示一个客户端配置文件。  
  
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
  
 可选的 `name` 属性唯一地标识了给定协定的终结点。 它由 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A> 或 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A> 用于指定客户端配置中的哪个终结点是目标终结点，必须在创建到服务的通道时加载。 通配符终结点配置名称“*”可用，并且指示 <xref:System.ServiceModel.ChannelFactory.ApplyConfiguration%2A> 方法，如果文件中正好有一个终结点配置，就应加载该终结点配置，否则引发异常。 如果省略此属性，则将对应的终结点用作与指定协定类型相关联的默认终结点。 `name` 属性的默认值是一个空字符串，它与任何其他名称一样进行匹配。  
  
 每个终结点都必须具有一个与之关联的地址，用于查找和标识终结点。 `address` 属性可用来指定提供终结点位置的 URL。 但是，通过创建统一资源标识符 (URI)，也可以在代码中指定服务终结点的地址，使用 <xref:System.ServiceModel.ServiceHost> 方法之一可以将该地址添加到 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>。 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)。 正如简介， [\<标头 >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)和[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)元素属于<xref:System.ServiceModel.EndpointAddress>和还讨论了[地址](../../../../docs/framework/wcf/feature-details/endpoint-addresses.md)主题。  
  
 `binding` 属性指示终结点在连接到服务时期望使用的绑定类型。 该类型必须具有一个已注册的配置节，才能加以引用。 在前面的示例中，这是[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)节，它指示终结点使用<xref:System.ServiceModel.WSHttpBinding>。 实际上，终结点可以使用某个给定类型的多个绑定。 其中每个具有其自己[\<绑定 >](../../../../docs/framework/misc/binding.md)在 (binding) 类型元素的元素。 `bindingconfiguration` 属性用于区分相同类型的绑定。 其值都与匹配`name`属性[\<绑定 >](../../../../docs/framework/misc/binding.md)元素。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]如何配置客户端绑定使用配置，请参阅[如何： 在配置中指定客户端绑定](../../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)。  
  
 `behaviorConfiguration`属性用于指定该[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)的[ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)终结点应使用。 其值都与匹配`name`属性[\<行为 >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)元素。 有关使用配置来指定客户端行为的示例，请参阅[配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)。  
  
 `contract` 属性指定终结点公开哪个协定。 此值对应于 <xref:System.ServiceModel.ServiceContractAttribute.ConfigurationName%2A> 的 <xref:System.ServiceModel.ServiceContractAttribute>。 默认值为实现相应服务的类的完整类型名。  
  
### <a name="configuring-metadata"></a>配置元数据  
 [\<元数据 >](../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)元素用于指定用于注册元数据的设置导入扩展。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]扩展元数据系统，请参阅[扩展元数据系统](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)。  
  
## <a name="see-also"></a>请参阅  
 [终结点：地址、绑定和协定](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [配置客户端行为](../../../../docs/framework/wcf/configuring-client-behaviors.md)
