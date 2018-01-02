---
title: '&lt;workflowRuntime&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2860c7ddd5f3d2f0ce2749c36afebcf9abfeac3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltworkflowruntimegt"></a><span data-ttu-id="1b370-102">&lt;workflowRuntime&gt;</span><span class="sxs-lookup"><span data-stu-id="1b370-102">&lt;workflowRuntime&gt;</span></span>
<span data-ttu-id="1b370-103">指定用于承载基于工作流的 <xref:System.Workflow.Runtime.WorkflowRuntime> 服务的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 实例的设置。</span><span class="sxs-lookup"><span data-stu-id="1b370-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span>  
  
 <span data-ttu-id="1b370-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1b370-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b370-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1b370-105">\<behaviors></span></span>  
<span data-ttu-id="1b370-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="1b370-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="1b370-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1b370-107">\<behavior></span></span>  
<span data-ttu-id="1b370-108">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="1b370-108">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b370-109">语法</span><span class="sxs-lookup"><span data-stu-id="1b370-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b370-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1b370-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1b370-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1b370-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b370-112">特性</span><span class="sxs-lookup"><span data-stu-id="1b370-112">Attributes</span></span>  
  
|<span data-ttu-id="1b370-113">特性</span><span class="sxs-lookup"><span data-stu-id="1b370-113">Attribute</span></span>|<span data-ttu-id="1b370-114">描述</span><span class="sxs-lookup"><span data-stu-id="1b370-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b370-115">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="1b370-115">cachedInstanceExpiration</span></span>|<span data-ttu-id="1b370-116">可选的 <xref:System.TimeSpan> 值，指定工作流实例可以在内存中保持空闲状态的最大时长，当超过这一时长后，将强制卸载或中止此实例。</span><span class="sxs-lookup"><span data-stu-id="1b370-116">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="1b370-117">如果 workflowruntime 具有执行 unloadOnIdle 的 `PersistenceService`，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="1b370-117">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="1b370-118">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="1b370-118">enablePerformanceCounters</span></span>|<span data-ttu-id="1b370-119">一个可选的布尔值，指定是否启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="1b370-119">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="1b370-120">性能计数器提供各种与工作流相关的统计信息，但在工作流运行时引擎启动和工作流实例运行时会造成性能下降。</span><span class="sxs-lookup"><span data-stu-id="1b370-120">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="1b370-121">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1b370-121">The default value is `true`.</span></span>|  
|<span data-ttu-id="1b370-122">name</span><span class="sxs-lookup"><span data-stu-id="1b370-122">name</span></span>|<span data-ttu-id="1b370-123">一个包含工作流运行时引擎的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="1b370-123">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="1b370-124">该名称在输出中使用，以便将此运行时与可能正在系统（例如，性能计数器）中运行的其他运行时区别开来。</span><span class="sxs-lookup"><span data-stu-id="1b370-124">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="1b370-125">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="1b370-125">The default is an empty string.</span></span>|  
|<span data-ttu-id="1b370-126">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="1b370-126">validateOnCreate</span></span>|<span data-ttu-id="1b370-127">一个可选的布尔值，指定在打开 WorkflowServiceHost 时是否进行工作流定义验证。</span><span class="sxs-lookup"><span data-stu-id="1b370-127">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="1b370-128">如果将此属性设置为 `true`，则在每次调用 `WorkflowServiceHost.Open` 时，都会执行工作流验证。</span><span class="sxs-lookup"><span data-stu-id="1b370-128">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="1b370-129">如果发现验证错误，则引发 <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> 错误。</span><span class="sxs-lookup"><span data-stu-id="1b370-129">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="1b370-130">如果将此属性设置为 `false`，则不进行工作流定义验证。</span><span class="sxs-lookup"><span data-stu-id="1b370-130">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="1b370-131">此属性的默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1b370-131">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b370-132">子元素</span><span class="sxs-lookup"><span data-stu-id="1b370-132">Child Elements</span></span>  
  
|<span data-ttu-id="1b370-133">元素</span><span class="sxs-lookup"><span data-stu-id="1b370-133">Element</span></span>|<span data-ttu-id="1b370-134">描述</span><span class="sxs-lookup"><span data-stu-id="1b370-134">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1b370-135">commonParameters</span><span class="sxs-lookup"><span data-stu-id="1b370-135">commonParameters</span></span>|<span data-ttu-id="1b370-136">服务使用的公用参数的集合。</span><span class="sxs-lookup"><span data-stu-id="1b370-136">A collection of common parameters used by services.</span></span> <span data-ttu-id="1b370-137">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="1b370-137">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="1b370-138">服务</span><span class="sxs-lookup"><span data-stu-id="1b370-138">services</span></span>|<span data-ttu-id="1b370-139">将添加到 <xref:System.Workflow.Runtime.WorkflowRuntime> 引擎的服务的集合。</span><span class="sxs-lookup"><span data-stu-id="1b370-139">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="1b370-140">这些元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="1b370-140">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="1b370-141">在集合中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="1b370-141">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="1b370-142">因此，在集合中指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="1b370-142">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="1b370-143">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="1b370-143">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1b370-144">父元素</span><span class="sxs-lookup"><span data-stu-id="1b370-144">Parent Elements</span></span>  
  
|<span data-ttu-id="1b370-145">元素</span><span class="sxs-lookup"><span data-stu-id="1b370-145">Element</span></span>|<span data-ttu-id="1b370-146">描述</span><span class="sxs-lookup"><span data-stu-id="1b370-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b370-147">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1b370-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="1b370-148">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="1b370-148">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1b370-149">备注</span><span class="sxs-lookup"><span data-stu-id="1b370-149">Remarks</span></span>  
 <span data-ttu-id="1b370-150">有关使用配置文件来控制的行为的详细信息<xref:System.Workflow.Runtime.WorkflowRuntime>对象的 Windows Workflow Foundation 宿主应用程序，请参阅[工作流配置文件](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)。</span><span class="sxs-lookup"><span data-stu-id="1b370-150">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b370-151">示例</span><span class="sxs-lookup"><span data-stu-id="1b370-151">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1b370-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b370-152">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="1b370-153">工作流配置文件</span><span class="sxs-lookup"><span data-stu-id="1b370-153">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
