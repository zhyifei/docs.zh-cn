---
title: '&lt;workflowIdle&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 66b2ff0db90a8126027eca976f73b3a8b554e3f4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltworkflowidlegt"></a>&lt;workflowIdle&gt;
一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。  
  
\<系统。ServiceModel >  
\<行为 >  
\<serviceBehaviors >  
\<行为 >  
\<workflowIdle >  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|timeToPersist|一个 Timespan 值，指定工作流进入空闲状态到变为保留的时间之间的持续时间。 默认值为 TimeSpan.MaxValue。<br /><br /> 该持续时间从工作流实例进入空闲状态时算起。 此属性是你想要同时为尽可能长时间在内存中保留实例更加主动地保留工作流实例的情况下很有用。 此属性才有效，其值是否小于**timeToUnload**属性。 如果大于该特性，将忽略此项。 如果此属性之前指定的值经过**timeToUnload**持久性工作流被卸载前必须完成的属性。 这意味着卸载操作可能要等到工作流永久保留完毕才能进行。 永久层负责处理暂时性错误的任何重试操作，并仅在发生不可恢复的错误时引发异常。 因此，任何在持久性操作期间引发的异常都将被视为是致命的，并导致该工作流实例中止。|  
|timeToUnload|一个 Timespan 值，该值指定工作流进入空闲状态与卸载工作流之间的持续时间。 默认值为 1 分钟。<br /><br /> 卸载一个工作流意味着该工作流已持久保存。 如果此属性设置为零持久保存工作流实例，并后立即卸载工作流进入空闲状态。 此属性设置为 TimeSpan.MaxValue 有效禁用卸载操作。 处于空闲状态的工作流实例永远不会被卸载。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 > 的\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|指定行为元素。|  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
