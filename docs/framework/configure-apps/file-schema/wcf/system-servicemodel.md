---
title: '&lt;system.serviceModel&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
ms.openlocfilehash: ef3af4663462ff2bb93622e128e58a3ac039dcf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ltsystemservicemodelgt"></a>&lt;system.serviceModel&gt;
此配置节包含所有 Windows Communication Foundation (WCF) ServiceModel 配置元素。  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.serviceModel>  
  <behaviors>  
  </behaviors>  
  <bindings>  
  </bindings>  
  <client>  
  </client>  
  <comContracts>  
  </comContracts>  
  <commonBehaviors>  
  </commonBehaviors>  
  <diagnostics>  
  </diagnostics>  
  <extensions>  
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>  
  <serviceHostingEnvironment>  
  </serviceHostingEnvironment>  
  <services>  
  </services>
  <standardEndpoints>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|此节定义名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。  每个集合分别定义终结点和服务所使用的行为元素。 每个行为元素由其唯一的 `name` 属性标识。|  
|[\<绑定 >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|此节包含标准绑定和自定义绑定的集合。 每一项均由其唯一的 `name` 进行标识。 服务通过用 `name` 与绑定进行链接来使用绑定。|  
|[\<客户端 >](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|此节包含客户端用来连接到服务的终结点的列表。|  
|[\<comContracts>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|此节定义支持 WCF 和 COM 互操作的 COM 协定。|  
|[\<commonBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|此节只能在 machine.config 文件中定义。 它定义了名为 `endpointBehaviors` 和 `serviceBehaviors` 的两个子集合。  每个集合定义分别使用的所有 WCF 终结点和在计算机上的服务行为元素。  如果中都定义一个行为`<commonBehaviors>`和`<behaviors>`部分中的行为\<行为 > 部分优先。|  
|[\<扩展 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|此节包含一个扩展集合，这些扩展使用户能够创建扩展的用户定义绑定、行为和其他方面。|  
|[\<诊断 >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|此节包含 WCF 的诊断功能设置。 用户可以启用/禁用跟踪、性能计数器和 WMI 提供程序，还可以添加自定义消息筛选器。|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|此节定义一组的传输协议方案 （例如，http、 net.tcp、 net.pipe 等） 和 WCF 绑定之间的默认协议映射。|  
|[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|此节定义一组路由筛选器，这些扩展名决定了类型的 Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter>时计算传入消息，以及路由表定义的目标终结点将消息发送到时要使用筛选器匹配。|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|此节定义服务承载环境要为特定传输实例化的类型。 如果此节为空，则使用默认类型。|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|此节包含服务的集合。 对于程序集中定义的每个服务，此元素包含一个为服务指定设置的 `service` 元素。|  
|[\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|此节定义一个标准终结点集合，这些终结点是预配置的可重用终结点。 标准终结点具有一个或多个设置为固定值的地址、绑定和协定特性。 例如，发现终结点具有固定的协定。 此外，还可以使用标准终结点用新属性扩展服务终结点，这与定义自定义绑定相似。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|\<configuration>|.NET 配置文件中的所有配置元素的根元素。|  
  
## <a name="remarks"></a>备注  
 WCF 不会向其他产品的配置节中添加元素。  
  
 WCF 服务中定义`services`配置文件节。 程序集可以包含任意多个服务。 每个服务都有自己的 `service` 配置节。 本节及其内容定义特定服务的服务协定、行为和终结点。  
  
 只有服务的 `name` 属性是必需的。  默认情况下，服务的名称描述用于实现服务的基础 CLR 类型；但是，您可以更改 <xref:System.ServiceModel.ServiceContractAttribute> 上的 ConfigurationName 属性以重写 CLR 类型要求。  
  
 `behaviorConfiguration` 属性是可选项。 它标识服务所使用的服务行为。 此属性指定的行为必须链接到同一配置文件的范围（即，同一文件或父文件）中定义的服务行为。  
  
 每个服务将公开 `endpoint` 元素中定义的一个或多个终结点。 每个终结点都具有自己的地址和绑定。 配置文件中使用的所有绑定都必须在该文件的范围内定义。  
  
 绑定通过 `name` 和 `bindingConfiguration` 属性的组合链接到终结点。 `binding` 属性定义在哪个节中定义绑定。 `bindingConfiguration` 属性定义使用绑定节中的哪个已配置绑定。 绑定节可以定义若干个已配置的绑定。  
  
## <a name="example"></a>示例  
 下面是 WCF 配置文件的示例。  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
           <!-- List of Behaviors -->  
        </behaviors>  
        <client>  
           <!-- List of Endpoints -->  
        </client>  
        <diagnostics wmiProviderEnabled="false" performanceCountersEnabled="false" tracingEnabled="false">  
        </diagnostics>  
        <serviceHostingEnvironment>  
           <!-- List of entries -->  
        </serviceHostingEnvironment>  
        <comContracts>  
           <!-- List of COM+ Contracts -->  
        </comContracts>          
        <services>  
           <!-- List of Services -->  
        </services>  
        <bindings>  
           <!-- List of Bindings -->  
        </bindings>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
