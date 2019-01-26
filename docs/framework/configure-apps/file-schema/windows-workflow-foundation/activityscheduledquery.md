---
title: '&lt;activityScheduledQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 0e69c32a7c292fda90828396c402c95e4899600a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687435"
---
# <a name="ltactivityscheduledquerygt"></a>&lt;activityScheduledQuery&gt;
表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。 跟踪参与者需要用此查询来订阅活动安排记录。  
  
 有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<tracking>  
\<trackingProfile>  
\<workflow>  
\<activityScheduledQueries>  
\<activityScheduledQuery>  
  
## <a name="syntax"></a>语法  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|activityName|一个字符串，指定正在请求取消的活动的名称。|  
|childActivityName|一个字符串，指定已请求将其取消的子活动的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<activityScheduledQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|一个查询，用于跟踪安排给父活动来执行的活动。|  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
