---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: a92a81062e92f832be78af2bfd75270390eaac3e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919492"
---
# <a name="commonparameters"></a><span data-ttu-id="59d24-101">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="59d24-101">\<commonParameters></span></span>
<span data-ttu-id="59d24-102">表示在多个服务之间全局使用的参数的集合。</span><span class="sxs-lookup"><span data-stu-id="59d24-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="59d24-103">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="59d24-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="59d24-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="59d24-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="59d24-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="59d24-105">\<behaviors></span></span>  
<span data-ttu-id="59d24-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="59d24-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="59d24-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="59d24-107">\<behavior></span></span>  
<span data-ttu-id="59d24-108">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="59d24-108">\<workflowRuntime></span></span>  
<span data-ttu-id="59d24-109">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="59d24-109">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59d24-110">语法</span><span class="sxs-lookup"><span data-stu-id="59d24-110">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59d24-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59d24-111">Attributes and Elements</span></span>  
 <span data-ttu-id="59d24-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59d24-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59d24-113">特性</span><span class="sxs-lookup"><span data-stu-id="59d24-113">Attributes</span></span>  
 <span data-ttu-id="59d24-114">无。</span><span class="sxs-lookup"><span data-stu-id="59d24-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="59d24-115">子元素</span><span class="sxs-lookup"><span data-stu-id="59d24-115">Child Elements</span></span>  
  
|<span data-ttu-id="59d24-116">元素</span><span class="sxs-lookup"><span data-stu-id="59d24-116">Element</span></span>|<span data-ttu-id="59d24-117">描述</span><span class="sxs-lookup"><span data-stu-id="59d24-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59d24-118">\<add></span><span class="sxs-lookup"><span data-stu-id="59d24-118">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="59d24-119">将服务使用的公共参数的名称/值对添加到集合。</span><span class="sxs-lookup"><span data-stu-id="59d24-119">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="59d24-120">父元素</span><span class="sxs-lookup"><span data-stu-id="59d24-120">Parent Elements</span></span>  
  
|<span data-ttu-id="59d24-121">元素</span><span class="sxs-lookup"><span data-stu-id="59d24-121">Element</span></span>|<span data-ttu-id="59d24-122">描述</span><span class="sxs-lookup"><span data-stu-id="59d24-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59d24-123">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="59d24-123">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="59d24-124">指定用于承载基于工作流<xref:System.Workflow.Runtime.WorkflowRuntime>的 Windows Communication Foundation (WCF) 服务的实例的设置。</span><span class="sxs-lookup"><span data-stu-id="59d24-124">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59d24-125">备注</span><span class="sxs-lookup"><span data-stu-id="59d24-125">Remarks</span></span>  
 <span data-ttu-id="59d24-126">`<commonParameters>` 元素定义在多个服务之间全局使用的任何参数，例如，使用 `ConnectionString` 时的<xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。</span><span class="sxs-lookup"><span data-stu-id="59d24-126">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59d24-127">如果在 `ConnectionString` 一节中指定了 `<commonParameters>` 值，则 SQL Tracking 服务并不始终使用该值。</span><span class="sxs-lookup"><span data-stu-id="59d24-127">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="59d24-128">它的某些操作可能会失败，例如检索 `StateMachineWorkflowInstance.StateHistory` 属性。</span><span class="sxs-lookup"><span data-stu-id="59d24-128">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="59d24-129">若要解决此问题，请在跟踪提供程序的配置节指定 `ConnectionString` 属性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="59d24-129">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="59d24-130">对于提交批处理工作进行永久性存储的服务，如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 和 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>，可以通过使用 `EnableRetries` 参数来允许它们重试其事务，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="59d24-130">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<workflowRuntime name="SampleApplication"
                 unloadOnIdle="false">
  <commonParameters>
    <add name="ConnectionString"
         value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
    <add name="EnableRetries"
         value="True" />
  </commonParameters>
  <services>
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime,
               Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="59d24-131">请注意, `EnableRetries`参数可以在全局级别设置 (如*CommonParameters*部分所示), 也可以为支持`EnableRetries`的个别服务设置 (如 "*服务*" 一节中所示)。</span><span class="sxs-lookup"><span data-stu-id="59d24-131">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="59d24-132">下面的示例代码演示如何通过编程方式更改公共参数。</span><span class="sxs-lookup"><span data-stu-id="59d24-132">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="59d24-133">有关使用配置文件控制 Windows Workflow Foundation 主机应用程序的<xref:System.Workflow.Runtime.WorkflowRuntime>对象的行为的详细信息, 请参阅[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="59d24-133">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59d24-134">示例</span><span class="sxs-lookup"><span data-stu-id="59d24-134">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="59d24-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="59d24-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="59d24-136">[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="59d24-136">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="59d24-137">\<add></span><span class="sxs-lookup"><span data-stu-id="59d24-137">\<add></span></span>](add-of-commonparameters.md)
