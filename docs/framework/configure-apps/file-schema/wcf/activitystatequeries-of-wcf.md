---
title: <activityStateQueries>WCF 的
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 415cd4a75ecab725f91bcd298f8a7966ea6079d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920299"
---
# <a name="activitystatequeries-of-wcf"></a>\<WCF 的 Activitystatequeries&gt >

表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。 例如, 你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。 跟踪参与者需要用此查询来订阅活动状态记录对象。 在 ActivityStates 中指定了要订阅的可用状态。

有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。

\<system.serviceModel>  
\<跟踪 >  
\<配置文件 >  
\<trackingProfile>  
\<工作流 >  
\<activityStateQueries>  

## <a name="syntax"></a>语法  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
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
|[\<activityStateQuery>](activitystatequery-of-wcf.md)|一个查询，用于跟踪在活动中发生的错误的处理。  每次 FaultHandler 处理错误时，都会发生此事件。|

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|[\<workflow>](../windows-workflow-foundation/workflow.md)|一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。|

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [工作流跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)
