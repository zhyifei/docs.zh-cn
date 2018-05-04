---
title: '&lt;discoveryClient&gt;'
ms.date: 03/30/2017
ms.assetid: a78f74c3-1152-4149-ab29-3f12d316caeb
ms.openlocfilehash: 8c69104b9eb1097ef5dc94c9aae7352d4949668f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltdiscoveryclientgt"></a>&lt;discoveryClient&gt;
一个用于创建自定义绑定的配置元素，通过该绑定，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。  
  
\<system.serviceModel>  
\<绑定 >  
\<customBinding>  
\<绑定 >  
\<discoveryClient >  
  
## <a name="syntax"></a>语法  
  
```xml  
<discoveryClient discoveryEndpoint="String" >
  <findCriteria duration="TimeSpan" maxResults="Integer" scopeMatchBy="Uri">
    <contractTypeNames>
      <add name="String" namespace="String" />
    <contractTypeNames>
    <extensions />
    <scopes>
      <add scope="URI"/>
    </scopes>
  </findCriteria>
</discoveryClient>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|discoveryEndpoint|一个包含发现终结点名称的字符串。通过此终结点，客户端应用程序能够自动搜索可检测服务，并能够在运行时查找服务地址。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。 条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续的时长）。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<绑定 >](../../../../../docs/framework/misc/binding.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement>  
 <xref:System.ServiceModel.Discovery.Configuration.DiscoveryClientElement>
