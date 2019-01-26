---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 5bc2e3ffeb93bdfcd45638d6b50e218c03706f42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520680"
---
# <a name="ltcancelrequestedqueriesgt"></a>&lt;cancelRequestedQueries&gt;
表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。 跟踪参与者需要用此查询来订阅取消请求记录对象。  
  
 有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<tracking>  
\<trackingProfile>  
\<workflow>  
\<cancelRequestedQueries>  
  
## <a name="syntax"></a>语法  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<cancelRequestedQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|一个查询，用于跟踪父活动取消子活动的请求|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<workflow>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。|  
  
## <a name="see-also"></a>请参阅
- [工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
