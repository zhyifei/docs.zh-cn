---
title: <behavior> 的 <serviceBehaviors>
ms.date: 03/30/2017
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
ms.openlocfilehash: 8c847368934cc4cd8ccaab017ede00b7b8963897
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926408"
---
# <a name="behavior-of-servicebehaviors"></a>\<serviceBehaviors > 的\<行为 >
`behavior` 元素包含服务行为的设置集合。 每个行为都按其 `name` 进行索引。 服务可以使用`behaviorConfiguration` [ \<端点 >](endpoint-element.md)元素的属性, 通过此名称链接到每个行为。 这样，终结点可以共享公共行为配置而不用重新定义设置。 从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。 有关默认配置和无值绑定和行为的详细信息, 请参阅[WCF 服务的](../../../wcf/samples/simplified-configuration-for-wcf-services.md)[简化配置](../../../wcf/simplified-configuration.md)和简化配置。  
  
> [!NOTE]
> 特定于 Windows 工作流活动的行为元素, 例如[ \<sendMessageChannelCache >](../windows-workflow-foundation/sendmessagechannelcache.md)元素, 在[ \< \<serviceBehaviors > 页的行为 >](../windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)中进行了介绍。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <serviceBehaviors>
       <behavior name="String" />
    </serviceBehaviors>
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
|[\<dataContractSerializer>](datacontractserializer-element.md)|包含 DataContractSerializer 的配置数据。|  
|[\<persistenceProvider>](persistenceprovider.md)|指定要使用的持久性提供程序实现的类型以及用于持久性操作的超时值。|  
|[\<routing>](routing-of-servicebehavior.md)|提供对路由服务的运行时访问以允许对路由配置进行动态修改。|  
|[\<serviceAuthenticationManager>](serviceauthenticationmanager.md)|提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。|  
|[\<serviceAuthorization>](serviceauthorization-element.md)|指定用于授予服务操作访问权限的设置。|  
|[\<serviceCredentials>](servicecredentials.md)|指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。|  
|[\<serviceDebug>](servicedebug.md)|指定 Windows Communication Foundation (WCF) 服务的调试和帮助信息功能。|  
|[\<serviceDiscovery>](servicediscovery.md)|指定服务终结点的可发现性。|  
|[\<serviceMetadata>](servicemetadata.md)|指定服务元数据的发布和相关信息。|  
|[\<serviceSecurityAudit>](servicesecurityaudit.md)|指定用于在服务操作过程中启用安全事件审核的设置。|  
|[\<serviceThrottling>](servicethrottling.md)|指定 WCF 服务的限制机制。|  
|[\<serviceTimeouts>](servicetimeouts.md)|指定服务的超时。|  
|[\<workflowRuntime>](workflowruntime.md)|指定用于承载基于工作流的 WCF 服务的 WorkflowRuntime 实例的设置。|  
|[\<useRequestHeadersForMetadataAddress>](userequestheadersformetadataaddress.md)|允许从请求消息头中检索元数据地址信息。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<serviceBehaviors>](servicebehaviors.md)|服务行为元素的集合。|
