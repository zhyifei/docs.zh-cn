---
title: WCF 的 &lt;activityScheduledQueries&gt;
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 35bcb0dc0c33d30eee566869579edb32f131f495
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374356"
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a>WCF 的 &lt;activityScheduledQueries&gt;
表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。 跟踪参与者需要用此查询来订阅活动安排记录。  
  
有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<跟踪 >  
\<配置文件 >  
\<trackingProfile>  
\<工作流 >  
\<activityScheduledQueries >  
  
## <a name="syntax"></a>语法  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"   
                                  childActivityName="String"/>
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  

无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<activityScheduledQuery >](activityscheduledquery-of-wcf.md)|一个查询，用于跟踪安排给父活动来执行的活动。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<工作流 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。|  
  
## <a name="see-also"></a>请参阅  

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
