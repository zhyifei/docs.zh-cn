---
title: <behavior> 的 <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: f14e80798a9b088508f23d718c8b386286ad65a3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919840"
---
# <a name="behavior-of-endpointbehaviors"></a>\<endpointBehaviors > 的\<行为 >
`behavior` 元素包含终结点行为的设置集合。 每个行为都按其 `name` 进行索引。 终结点可以通过此名称链接到每个行为。 从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。 有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。  
  
 \<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|NAME|一个包含行为的配置名称的唯一字符串。 此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。 从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。 有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|指定用于向服务验证客户端身份的凭据。|  
|[\<callbackDebug>](callbackdebug.md)|指定 Windows Communication Foundation (WCF) 回调对象的服务调试。|  
|[\<callbackTimeouts>](callbacktimeouts.md)|指定客户端回调的超时。|  
|[\<clientVia>](clientvia.md)|指定消息应采用的路由。|  
|[\<dataContractSerializer>](datacontractserializer.md)|包含 DataContractSerializer 的配置数据。|  
|[\<dispatcherSynchronization>](dispatchersynchronization.md)|指定允许服务进行异步答复的终结点行为。|  
|[\<enableWebScript>](enablewebscript.md)|启用终结点行为，此行为使得可以使用 ASP.NET AJAX 网页中的服务。 该行为只应与\<webHttpBinding > 标准绑定\<或 w > 绑定元素一起使用。|  
|[\<endpointDiscovery>](endpointdiscovery.md)|指定终结点的各种发现设置，例如终结点的可发现性、范围以及对终结点元数据的任何自定义扩展。|  
|[\<soapProcessing>](soapprocessing.md)|定义用于封送不同绑定类型和消息版本之间消息的客户端终结点行为。|  
|[\<synchronousReceive>](synchronousreceive-element.md)|指定服务或客户端应用程序中用于接收消息的运行时行为。 它不具有任何属性或子元素。|  
|[\<transactedBatching>](transactedbatching.md)|指定接收操作是否支持事务批处理。|  
|[\<webHttp>](webhttp.md)|通过配置指定终结点上的 WebHttpBehavior。 此行为与\<webHttpBinding > 标准绑定结合使用时, 将为 WCF 服务启用 Web 编程模型。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<endpointBehaviors>](endpointbehaviors.md)|终结点行为元素的集合。|
