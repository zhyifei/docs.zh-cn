---
title: '&lt;commonParameters&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: efd4f37adb19940e81109924c3ec313d71bf6e7f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcommonparametersgt"></a><span data-ttu-id="e3d52-102">&lt;commonParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="e3d52-102">&lt;commonParameters&gt;</span></span>
<span data-ttu-id="e3d52-103">表示在多个服务之间全局使用的参数的集合。</span><span class="sxs-lookup"><span data-stu-id="e3d52-103">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="e3d52-104">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="e3d52-104">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="e3d52-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e3d52-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="e3d52-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e3d52-106">\<behaviors></span></span>  
<span data-ttu-id="e3d52-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e3d52-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="e3d52-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="e3d52-108">\<behavior></span></span>  
<span data-ttu-id="e3d52-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="e3d52-109">\<workflowRuntime></span></span>  
<span data-ttu-id="e3d52-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="e3d52-110">\<commonParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d52-111">语法</span><span class="sxs-lookup"><span data-stu-id="e3d52-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3d52-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3d52-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e3d52-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e3d52-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3d52-114">特性</span><span class="sxs-lookup"><span data-stu-id="e3d52-114">Attributes</span></span>  
 <span data-ttu-id="e3d52-115">无。</span><span class="sxs-lookup"><span data-stu-id="e3d52-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3d52-116">子元素</span><span class="sxs-lookup"><span data-stu-id="e3d52-116">Child Elements</span></span>  
  
|<span data-ttu-id="e3d52-117">元素</span><span class="sxs-lookup"><span data-stu-id="e3d52-117">Element</span></span>|<span data-ttu-id="e3d52-118">描述</span><span class="sxs-lookup"><span data-stu-id="e3d52-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3d52-119">\<add></span><span class="sxs-lookup"><span data-stu-id="e3d52-119">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|<span data-ttu-id="e3d52-120">将服务使用的公共参数的名称/值对添加到集合。</span><span class="sxs-lookup"><span data-stu-id="e3d52-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3d52-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e3d52-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e3d52-122">元素</span><span class="sxs-lookup"><span data-stu-id="e3d52-122">Element</span></span>|<span data-ttu-id="e3d52-123">描述</span><span class="sxs-lookup"><span data-stu-id="e3d52-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3d52-124">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="e3d52-124">\<workflowRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|<span data-ttu-id="e3d52-125">指定用于承载基于工作流的 <xref:System.Workflow.Runtime.WorkflowRuntime> 服务的 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 实例的设置。</span><span class="sxs-lookup"><span data-stu-id="e3d52-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3d52-126">备注</span><span class="sxs-lookup"><span data-stu-id="e3d52-126">Remarks</span></span>  
 <span data-ttu-id="e3d52-127">`<commonParameters>` 元素定义在多个服务之间全局使用的任何参数，例如，使用 `ConnectionString` 时的<xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。</span><span class="sxs-lookup"><span data-stu-id="e3d52-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3d52-128">如果在 `ConnectionString` 一节中指定了 `<commonParameters>` 值，则 SQL Tracking 服务并不始终使用该值。</span><span class="sxs-lookup"><span data-stu-id="e3d52-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="e3d52-129">它的某些操作可能会失败，例如检索 `StateMachineWorkflowInstance.StateHistory` 属性。</span><span class="sxs-lookup"><span data-stu-id="e3d52-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="e3d52-130">若要解决此问题，请在跟踪提供程序的配置节指定 `ConnectionString` 属性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e3d52-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 <span data-ttu-id="e3d52-131">对于提交批处理工作进行永久性存储的服务，如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 和 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>，可以通过使用 `EnableRetries` 参数来允许它们重试其事务，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="e3d52-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
```xml  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 <span data-ttu-id="e3d52-132">请注意，`EnableRetries`参数可设置在全局级别 (如中所示*CommonParameters*部分) 或为个别服务支持`EnableRetries`(中所示*服务*部分)。</span><span class="sxs-lookup"><span data-stu-id="e3d52-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="e3d52-133">下面的示例代码演示如何通过编程方式更改公共参数。</span><span class="sxs-lookup"><span data-stu-id="e3d52-133">The following sample code shows how to change the common parameters programmatically.</span></span>  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="e3d52-134">有关如何使用配置文件来控制的行为的详细信息<xref:System.Workflow.Runtime.WorkflowRuntime>对象的 Windows Workflow Foundation 宿主应用程序，请参阅[工作流配置文件](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)。</span><span class="sxs-lookup"><span data-stu-id="e3d52-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e3d52-135">示例</span><span class="sxs-lookup"><span data-stu-id="e3d52-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3d52-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3d52-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="e3d52-137">工作流配置文件</span><span class="sxs-lookup"><span data-stu-id="e3d52-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="e3d52-138">\<add></span><span class="sxs-lookup"><span data-stu-id="e3d52-138">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)
