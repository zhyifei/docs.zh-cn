---
title: <workflowRuntime>
ms.date: 03/30/2017
ms.assetid: 304c70fa-78d1-4d0f-b89f-0ca23d734c6f
ms.openlocfilehash: 0cd04f66cc4b73eb5f1c43bd6c8dc9189dfceff1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915214"
---
# <a name="workflowruntime"></a><span data-ttu-id="0efd4-101">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="0efd4-101">\<workflowRuntime></span></span>
<span data-ttu-id="0efd4-102">指定用于承载基于工作流<xref:System.Workflow.Runtime.WorkflowRuntime>的 Windows Communication Foundation (WCF) 服务的实例的设置。</span><span class="sxs-lookup"><span data-stu-id="0efd4-102">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>  
  
 <span data-ttu-id="0efd4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0efd4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0efd4-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="0efd4-104">\<behaviors></span></span>  
<span data-ttu-id="0efd4-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0efd4-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="0efd4-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="0efd4-106">\<behavior></span></span>  
<span data-ttu-id="0efd4-107">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="0efd4-107">\<workflowRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0efd4-108">语法</span><span class="sxs-lookup"><span data-stu-id="0efd4-108">Syntax</span></span>  
  
```xml  
<workflowRuntime cachedInstanceExpiration="TimeSpan"
                 enablePerformanceCounters="Boolean"
                 name="String"
                 validateOnCreate="Boolean">
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0efd4-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0efd4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0efd4-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0efd4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0efd4-111">特性</span><span class="sxs-lookup"><span data-stu-id="0efd4-111">Attributes</span></span>  
  
|<span data-ttu-id="0efd4-112">特性</span><span class="sxs-lookup"><span data-stu-id="0efd4-112">Attribute</span></span>|<span data-ttu-id="0efd4-113">描述</span><span class="sxs-lookup"><span data-stu-id="0efd4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0efd4-114">cachedInstanceExpiration</span><span class="sxs-lookup"><span data-stu-id="0efd4-114">cachedInstanceExpiration</span></span>|<span data-ttu-id="0efd4-115">可选的 <xref:System.TimeSpan> 值，指定工作流实例可以在内存中保持空闲状态的最大时长，当超过这一时长后，将强制卸载或中止此实例。</span><span class="sxs-lookup"><span data-stu-id="0efd4-115">An optional <xref:System.TimeSpan> value that specifies the maximum duration a workflow instance can stay in-memory in idle state before it is forcefully unloaded or aborted.</span></span> <span data-ttu-id="0efd4-116">如果 workflowruntime 具有执行 unloadOnIdle 的 `PersistenceService`，则忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="0efd4-116">If the workflowruntime has `PersistenceService` which performs unloadOnIdle, this attribute is ignored.</span></span>|  
|<span data-ttu-id="0efd4-117">enablePerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="0efd4-117">enablePerformanceCounters</span></span>|<span data-ttu-id="0efd4-118">一个可选的布尔值，指定是否启用性能计数器。</span><span class="sxs-lookup"><span data-stu-id="0efd4-118">An optional Boolean value that specifies whether performance counters are enabled.</span></span> <span data-ttu-id="0efd4-119">性能计数器提供各种与工作流相关的统计信息，但在工作流运行时引擎启动和工作流实例运行时会造成性能下降。</span><span class="sxs-lookup"><span data-stu-id="0efd4-119">Performance counters provide information on various workflow-related statistics, but they cause a performance penalty when the workflow runtime engine starts, and when workflow instances are running.</span></span> <span data-ttu-id="0efd4-120">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0efd4-120">The default value is `true`.</span></span>|  
|<span data-ttu-id="0efd4-121">NAME</span><span class="sxs-lookup"><span data-stu-id="0efd4-121">name</span></span>|<span data-ttu-id="0efd4-122">一个包含工作流运行时引擎的名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0efd4-122">A string containing the name of the workflow runtime engine.</span></span> <span data-ttu-id="0efd4-123">该名称在输出中使用，以便将此运行时与可能正在系统（例如，性能计数器）中运行的其他运行时区别开来。</span><span class="sxs-lookup"><span data-stu-id="0efd4-123">The name is used in output to distinguish this runtime from other runtimes that may be running on the system, for example, in performance counters.</span></span><br /><br /> <span data-ttu-id="0efd4-124">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="0efd4-124">The default is an empty string.</span></span>|  
|<span data-ttu-id="0efd4-125">validateOnCreate</span><span class="sxs-lookup"><span data-stu-id="0efd4-125">validateOnCreate</span></span>|<span data-ttu-id="0efd4-126">一个可选的布尔值，指定在打开 WorkflowServiceHost 时是否进行工作流定义验证。</span><span class="sxs-lookup"><span data-stu-id="0efd4-126">An optional Boolean value that specifies whether validation of workflow definition will occur when the WorkflowServiceHost is opened.</span></span>  <span data-ttu-id="0efd4-127">如果将此属性设置为 `true`，则在每次调用 `WorkflowServiceHost.Open` 时，都会执行工作流验证。</span><span class="sxs-lookup"><span data-stu-id="0efd4-127">When this attribute is set to `true`, the workflow validation is executed every time `WorkflowServiceHost.Open` is called.</span></span> <span data-ttu-id="0efd4-128">如果发现验证错误，则引发 <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> 错误。</span><span class="sxs-lookup"><span data-stu-id="0efd4-128">If validation errors are found, a <xref:System.Workflow.ComponentModel.Compiler.WorkflowValidationFailedException> error is thrown.</span></span><br /><br /> <span data-ttu-id="0efd4-129">如果将此属性设置为 `false`，则不进行工作流定义验证。</span><span class="sxs-lookup"><span data-stu-id="0efd4-129">When this property is set to `false`, no Workflow definition validation will happen.</span></span><br /><br /> <span data-ttu-id="0efd4-130">此属性的默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="0efd4-130">The default value for this property is `true`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0efd4-131">子元素</span><span class="sxs-lookup"><span data-stu-id="0efd4-131">Child Elements</span></span>  
  
|<span data-ttu-id="0efd4-132">元素</span><span class="sxs-lookup"><span data-stu-id="0efd4-132">Element</span></span>|<span data-ttu-id="0efd4-133">描述</span><span class="sxs-lookup"><span data-stu-id="0efd4-133">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0efd4-134">commonParameters</span><span class="sxs-lookup"><span data-stu-id="0efd4-134">commonParameters</span></span>|<span data-ttu-id="0efd4-135">服务使用的公用参数的集合。</span><span class="sxs-lookup"><span data-stu-id="0efd4-135">A collection of common parameters used by services.</span></span> <span data-ttu-id="0efd4-136">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="0efd4-136">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
|<span data-ttu-id="0efd4-137">服务</span><span class="sxs-lookup"><span data-stu-id="0efd4-137">services</span></span>|<span data-ttu-id="0efd4-138">将添加到 <xref:System.Workflow.Runtime.WorkflowRuntime> 引擎的服务的集合。</span><span class="sxs-lookup"><span data-stu-id="0efd4-138">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="0efd4-139">这些元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="0efd4-139">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="0efd4-140">在集合中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="0efd4-140">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="0efd4-141">因此，在集合中指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="0efd4-141">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="0efd4-142">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="0efd4-142">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0efd4-143">父元素</span><span class="sxs-lookup"><span data-stu-id="0efd4-143">Parent Elements</span></span>  
  
|<span data-ttu-id="0efd4-144">元素</span><span class="sxs-lookup"><span data-stu-id="0efd4-144">Element</span></span>|<span data-ttu-id="0efd4-145">描述</span><span class="sxs-lookup"><span data-stu-id="0efd4-145">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0efd4-146">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0efd4-146">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="0efd4-147">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="0efd4-147">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0efd4-148">备注</span><span class="sxs-lookup"><span data-stu-id="0efd4-148">Remarks</span></span>  
 <span data-ttu-id="0efd4-149">有关使用配置文件控制 Windows Workflow Foundation 主机应用程序的<xref:System.Workflow.Runtime.WorkflowRuntime>对象的行为的详细信息, 请参阅[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="0efd4-149">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0efd4-150">示例</span><span class="sxs-lookup"><span data-stu-id="0efd4-150">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0efd4-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="0efd4-151">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <span data-ttu-id="0efd4-152">[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0efd4-152">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
