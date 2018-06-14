---
title: '&lt;sqlWorkflowInstanceStore&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8a4e4214-fc51-4f4d-b968-0427c37a9520
ms.openlocfilehash: 223108502395311f0db19753addc2a3f2345beac
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757874"
---
# <a name="ltsqlworkflowinstancestoregt"></a>&lt;sqlWorkflowInstanceStore&gt;
允许你配置的服务行为<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>功能，支持到 SQL Server 2005 或 SQL Server 2008 数据库的工作流服务实例的保存状态信息。 有关此功能的详细信息，请参阅[SQL 工作流实例存储](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)。  
  
\<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<sqlWorkflowInstanceStore >  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sqlWorkflowInstanceStore connectionStringName="String" 
                                honstLockRenewalPeriod="TimeSpan" 
                                instanceCompletionAction="DeleteNothing/DeleteAll" 
                                instanceEncodingAction="None/GZip" 
                                instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                runnableInstancesDetectionPeriod="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|connectionString|包含用于连接到基础持久性数据库的连接字符串的字符串。|  
|connectionStringName|包含数据库服务器的已命名的连接字符串的字符串。 已命名的连接字符串的示例为"DefaultConnectionString"。|  
|honstLockRenewalPeriod|一个 Timespan 值，指定宿主必须在其间续订对某个实例的锁定的时间段。 如果宿主没有在指定的时间段内续订锁定，则会解除锁定此实例，并且另一宿主可能会选取此实例。<br /><br /> 卸载一个工作流意味着该工作流已持久保存。 如果此属性设置为零持久保存工作流实例，并后立即卸载工作流进入空闲状态。 此属性设置为 TimeSpan.MaxValue 有效禁用卸载操作。 处于空闲状态的工作流实例永远不会被卸载。|  
|instanceCompletionAction|一个值，指定在工作流实例完成之后，该工作流实例数据是保留在持久性存储区中还是被删除。 此值的类型为 <xref:System.Activities.DurableInstancing.InstanceCompletionAction>。<br /><br /> 枚举的操作包括在实例完成其操作后删除持久性存储区中的实例数据或不删除持久性存储区中的实例数据。<br /><br /> 完成实例之后保留实例会导致持久性数据库快速增大，这会影响数据库的性能。 您应当配置数据库清除策略来定期删除这些记录，以确保数据库的性能水平能够满足性能要求。|  
|instanceEncodingOption|一个可选值，指定在将实例状态信息保存到持久性存储区之前，是否使用 GZip 算法压缩此信息。 此值的类型为 `System.Activities.DurableInstancing.InstanceEncodingAction`。 此属性的可能值为"None"，它指定无压缩和"GZip"，指定该实例数据进行压缩，并使用 gzip 算法。|  
|instanceLockedExceptionAction|一个值，指定为响应在宿主尝试锁定当前已由另一宿主锁定的实例时引发的异常而发生的操作。 此值的类型为 <xref:System.Activities.DurableInstancing.InstanceLockedExceptionAction>。<br /><br /> 此字段的可选选项有：“无”、“基本重试”和“积极重试”。 默认值为 None。 下面逐一说明上述三个选项：<br /><br /> -   无。 服务主机不会尝试锁定实例，并将 <xref:System.Runtime.DurableInstancing.InstanceLockedException> 传递给调用方。<br />-基本重试。 服务主机将使用线性重试间隔重新尝试锁定实例，并在序列结尾将异常传递给调用方。<br />-积极重试。 服务主机将使用按指数增长的延迟时间重新尝试锁定实例，并在序列结尾将 <xref:System.Runtime.DurableInstancing.InstanceLockedException> 传递给调用方。|  
|runnableInstancesDetectionPeriod||  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 > 的\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|指定行为元素。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.SqlWorkflowInstanceStoreElement>  
 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>  
 [SQL 工作流实例存储](../../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md)
