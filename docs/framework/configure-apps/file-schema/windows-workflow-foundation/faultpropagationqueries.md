---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152126"
---
# <a name="faultpropagationqueries"></a>\<故障传播查询>
表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。  每次 FaultHandler 处理错误时，都会发生此事件。 应使用此类查询来跟踪对在活动中出现的错误进行的处理。 跟踪参与者需要用此查询来订阅错误传播记录。  
  
 有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪配置文件>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<故障传播查询>**
  
## <a name="syntax"></a>语法  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<故障传播查询>](faultpropagationquery.md)|一个查询，用于跟踪在活动中发生的错误的处理。  每次 FaultHandler 处理错误时，都会发生此事件。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<工作流>](workflow.md)|包含**活动定义 Id**属性标识的特定工作流的所有查询的配置元素。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [工作流跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)
