---
title: '&lt;workflowRuntime&gt;'
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 7c2bd4e2a8c1ddbdb98878d1d97c7acc41856310
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755843"
---
# <a name="ltworkflowruntimegt"></a>&lt;workflowRuntime&gt;
指定的实例的设置<xref:System.Workflow.Runtime.WorkflowRuntime>用于承载基于工作流的 Windows Communication Foundation (WCF) 服务。  
  
 \<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<workflowRuntime>  
  
## <a name="syntax"></a>语法  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"  
                                  enablePerformanceCounters="Boolean"  
                                  name="String"  
                                  validateOnCreate="Boolean">  
                 <commonParameters>  
                    <add name="String" value="String" />  
                 </commonParameters>  
                 <services>  
                    <add type="String"/>  
                 </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|cachedInstanceExpiration|可选的 <xref:System.TimeSpan> 值，指定工作流实例可以在内存中保持空闲状态的最大时长，当超过这一时长后，将强制卸载或中止此实例。 如果 workflowruntime 具有执行 unloadOnIdle 的 `PersistenceService`，则忽略此属性。|  
|enablePerformanceCounters|一个可选的布尔值，指定是否启用性能计数器。 性能计数器提供各种与工作流相关的统计信息，但在工作流运行时引擎启动和工作流实例运行时会造成性能下降。 默认值为 `true`。|  
|name|一个包含工作流运行时引擎的名称的字符串。 该名称在输出中使用，以便将此运行时与可能正在系统（例如，性能计数器）中运行的其他运行时区别开来。<br /><br /> 默认值为一个空字符串。|  
|validateOnCreate|一个可选的布尔值，指定在打开 WorkflowServiceHost 时是否进行工作流定义验证。  如果将此属性设置为 `true`，则在每次调用 `WorkflowServiceHost.Open` 时，都会执行工作流验证。 如果发现验证错误，则引发 <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> 错误。<br /><br /> 如果将此属性设置为 `false`，则不进行工作流定义验证。<br /><br /> 此属性的默认值为 `true`。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|commonParameters|服务使用的公用参数的集合。 此集合通常将包括可由持久性服务共享的数据库连接字符串。|  
|服务|将添加到 <xref:System.Workflow.Runtime.WorkflowRuntime> 引擎的服务的集合。 这些元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。  在集合中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。 因此，在集合中指定的服务必须遵循关于其构造函数的签名的某些规则。 有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定行为元素。|  
  
## <a name="remarks"></a>备注  
 有关使用配置文件来控制的行为的详细信息<xref:System.Workflow.Runtime.WorkflowRuntime>对象的 Windows Workflow Foundation 宿主应用程序，请参阅[工作流配置文件](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)。  
  
## <a name="example"></a>示例  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <commonParameters>  
            <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
            <add name="EnableRetries" value="True" />  
         </commonParameters>  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [工作流配置文件](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
