---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: f9e64e667befb70d617574b2a03c3e6bebb2a143
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925606"
---
# <a name="filtertable"></a>\<filterTable>
表示一个路由表, 该表包含用于评估消息的筛选器的列表, 以及在筛选器计算结果为 true 时要将消息路由到的客户端终结点。  
  
 \<system.serviceModel>  
\<路由 >  
\<routingTables>  
\<表 >  
  
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
  
|元素|描述|  
|-------------|-----------------|  
|NAME|一个字符串，包含此配置元素的唯一名称。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<routing>](routing.md)|一个包含路由表的配置节。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
