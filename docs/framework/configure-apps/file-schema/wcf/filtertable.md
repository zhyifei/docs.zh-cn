---
title: '&lt;filterTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 96425604fab8f70456ea1e0d97efb2c3bf843224
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltertablegt"></a>&lt;filterTable&gt;
表示包含要评估针对消息和消息路由到的客户端终结点，如果筛选器的计算结果为 true 的筛选器列表的路由表。  
  
 \<system.serviceModel >  
\<路由 >  
\<routingTables >  
\<表 >  
  
## <a name="syntax"></a>语法  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|元素|描述|  
|-------------|-----------------|  
|name|一个字符串，包含此配置元素的唯一名称。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<筛选器 >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|路由筛选器与在筛选器匹配时消息要发送到的目标终结点之间的映射。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|一个包含路由表的配置节。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
