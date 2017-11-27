---
title: '&lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 95be974404fdd845ee3a24bb194e9ba5e890147d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcontracttypenamesgt"></a>&lt;contractTypeNames&gt;
一个指定协定类型名称列表的配置节，这些名称是所搜索服务的协定名称以及搜索服务时通常采用的条件。 如果指定多个协定名称，则只有与全部协定都匹配的服务终结点才会进行答复。 请注意，在 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 中，一个终结点只能支持一个协定。  
  
 \<系统。ServiceModel >  
\<standardEndpoints >  
  
## <a name="syntax"></a>语法  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan" 
                        maxResults="Integer" 
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String" namespace="String" />
            <contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI"/>
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|协定类型名称是一个属性，它引用搜索服务时通常采用的条件集。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<findCriteria >](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|一个配置元素，提供客户端应用程序用于搜索发现服务的一组条件。 条件可以划分为搜索条件 （指定要查找的服务） 和查找终止条件 （搜索应持续的时长）。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
