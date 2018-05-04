---
title: '&lt;state&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 327a5e98a9ecf6ba23eaf47c3d6d73bfb7852ee7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltstategt"></a>&lt;state&gt;
表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。  
  
 有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<跟踪 >  
\<trackingProfile>  
\<工作流 >  
\<workflowInstanceQueries>  
\<workflowInstanceQuery >  
\<状态 >  
\<状态 >  
  
## <a name="syntax"></a>语法  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。|  
  
## <a name="remarks"></a>备注  
 返回的记录由此集合中的状态进行筛选。  
  
 下表中列出了可能的状态值。  
  
|状态|描述|  
|-----------|-----------------|  
|Aborted|工作流实例已中止。|  
|已完成|工作流实例已完成。|  
|Deleted|工作流实例已删除。|  
|Idle|工作流实例处于空闲状态。|  
|Persisted|工作流实例已保留。|  
|Resumed|工作流实例已恢复。|  
|Started|工作流实例已启动。|  
|UnhandledException|工作流实例遇到了未经处理的异常。|  
|Unloaded|工作流实例已卸载。|  
|Canceled|工作流实例已取消。|  
|挂起|工作流实例处于挂起状态。|  
|Terminated|工作流实例已终止。|  
|Unsuspended|工作流实例已取消挂起。|  
  
## <a name="example"></a>示例  
 下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>      
 [工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
