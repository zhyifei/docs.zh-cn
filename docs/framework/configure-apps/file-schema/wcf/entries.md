---
title: '&lt;entries&gt;'
ms.date: 03/30/2017
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
ms.openlocfilehash: 33f98cb4b138307622a14463ce5a3008058b6e31
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587055"
---
# <a name="ltentriesgt"></a>&lt;entries&gt;
一个路由项，包含路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。  
  
 \<system.serviceModel>  
\<路由 >  
\<routingTables>  
\<table>  
\<entries>  
  
## <a name="syntax"></a>语法  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<filters>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|将筛选器映射到以前定义的客户端终结点。 与此筛选器匹配的消息将发送到此目标。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|一个包含路由表的配置节。|  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement?displayProperty=nameWithType>
