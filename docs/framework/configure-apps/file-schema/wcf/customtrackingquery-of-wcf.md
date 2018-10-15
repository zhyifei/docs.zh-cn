---
title: WCF 的 &lt;customTrackingQuery&gt;
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: e13064afbd9f5dbc8d7216eb384001e1e005785c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316228"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a>WCF 的 &lt;customTrackingQuery&gt;

表示用于跟踪你代码活动中定义的事件的查询。 跟踪参与者需要用此查询来订阅自定义跟踪记录。

有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<跟踪 >  
\<配置文件 >  
\<trackingProfile>  
\<工作流 >  
\<customTrackingQueries >  
\<customTrackingQuery >  
  
## <a name="syntax"></a>语法  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a>特性和元素  

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`activityName`|一个字符串，指定生成跟踪记录的活动的名称。|  
|`name`|一个字符串，指定发出的自定义跟踪记录的名称。|  
  
### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|  
|-------------|-----------------|  
|[\<customTrackingQueries>](customtrackingqueries-of-wcf.md)|表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。|
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
