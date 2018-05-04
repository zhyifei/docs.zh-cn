---
title: '&lt;endpointDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: c5971ce79ac2f03fbdc91653d5d282804e98cf8a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltendpointdiscoverygt"></a>&lt;endpointDiscovery&gt;
指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。  
  
\<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
\<endpointDiscovery >  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|一个布尔值，指定是否对此终结点启用可发现性。 默认值为 `false`。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<作用域 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|终结点的范围 URI 集合。 一个终结点可以与多个范围 URI 关联。|  
|[\<扩展 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [的\<endpointDiscovery >]|一个 XML 元素集合，用于指定要对终结点发布的自定义元数据。|  
|\<类型 >|要搜索的接口集合。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定行为元素。|  
|||  
  
## <a name="remarks"></a>备注  
 如果将此配置元素添加到终结点的行为配置，并将 `enabled` 特性设置为 `true`，此配置元素将启用该终结点的可发现性。 此外，你可以使用[\<作用域 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)与指定自定义范围 Uri 可以用于在查询时筛选服务终结点的子元素以及[\<扩展 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md)子元素可指定应随标准可发现元数据 （EPR、 ContractTypeName、 BindingName、 作用域和 ListenURI） 一起发布的自定义元数据。  
  
 此配置元素是依赖于[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)提供可发现性服务级别控制的元素。 这意味着如果将忽略此元素的设置[ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)不是配置中存在。  
  
## <a name="example"></a>示例  
 下面的配置示例指定要对终结点发布的筛选范围和扩展元数据。  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
