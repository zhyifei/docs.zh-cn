---
title: "&lt;commonParameters&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb11f83ed2b7d3d371d7dc5475f4ce3672bb8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="8e2b1-102">&lt;commonParameters&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="8e2b1-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="8e2b1-103">指定在多个服务之间全局使用的参数的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="8e2b1-104">此参数通常包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="8e2b1-105">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8e2b1-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-106">\<behaviors></span></span>  
<span data-ttu-id="8e2b1-107">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="8e2b1-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-108">\<behavior></span></span>  
<span data-ttu-id="8e2b1-109">\<workflowRuntime ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-109">\<workflowRuntime></span></span>  
<span data-ttu-id="8e2b1-110">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-110">\<commonParameters></span></span>  
<span data-ttu-id="8e2b1-111">\<add></span><span class="sxs-lookup"><span data-stu-id="8e2b1-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e2b1-112">语法</span><span class="sxs-lookup"><span data-stu-id="8e2b1-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e2b1-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8e2b1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="8e2b1-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e2b1-115">特性</span><span class="sxs-lookup"><span data-stu-id="8e2b1-115">Attributes</span></span>  
  
|<span data-ttu-id="8e2b1-116">特性</span><span class="sxs-lookup"><span data-stu-id="8e2b1-116">Attribute</span></span>|<span data-ttu-id="8e2b1-117">描述</span><span class="sxs-lookup"><span data-stu-id="8e2b1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e2b1-118">name</span><span class="sxs-lookup"><span data-stu-id="8e2b1-118">name</span></span>|<span data-ttu-id="8e2b1-119">为服务指定的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="8e2b1-120">值</span><span class="sxs-lookup"><span data-stu-id="8e2b1-120">value</span></span>|<span data-ttu-id="8e2b1-121">为服务指定的参数的值。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e2b1-122">子元素</span><span class="sxs-lookup"><span data-stu-id="8e2b1-122">Child Elements</span></span>  
 <span data-ttu-id="8e2b1-123">无。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e2b1-124">父元素</span><span class="sxs-lookup"><span data-stu-id="8e2b1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8e2b1-125">元素</span><span class="sxs-lookup"><span data-stu-id="8e2b1-125">Element</span></span>|<span data-ttu-id="8e2b1-126">描述</span><span class="sxs-lookup"><span data-stu-id="8e2b1-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e2b1-127">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-127">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="8e2b1-128">服务使用的公用参数的集合。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="8e2b1-129">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e2b1-130">备注</span><span class="sxs-lookup"><span data-stu-id="8e2b1-130">Remarks</span></span>  
 <span data-ttu-id="8e2b1-131">`<commonParameters>` 元素定义在多个服务之间全局使用的任何参数，例如，使用 `ConnectionString` 时的<xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="8e2b1-132">对于提交批处理工作进行永久性存储的服务，如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 和 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>，可以通过使用 `EnableRetries` 参数来允许它们重试其事务，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8e2b1-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="8e2b1-133">请注意，`EnableRetries`参数都可以设置在全局级别 (如中所示*CommonParameters*部分) 或为个别服务支持`EnableRetries`(中所示*服务*部分)。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="8e2b1-134">有关使用配置文件来控制的行为的详细信息<xref:System.Workflow.Runtime.WorkflowRuntime>对象的 Windows Workflow Foundation 宿主应用程序，请参阅[工作流配置文件](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)。</span><span class="sxs-lookup"><span data-stu-id="8e2b1-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e2b1-135">示例</span><span class="sxs-lookup"><span data-stu-id="8e2b1-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e2b1-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e2b1-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 [<span data-ttu-id="8e2b1-137">工作流配置文件</span><span class="sxs-lookup"><span data-stu-id="8e2b1-137">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/en-us/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)  
 [<span data-ttu-id="8e2b1-138">\<commonParameters ></span><span class="sxs-lookup"><span data-stu-id="8e2b1-138">\<commonParameters></span></span>](http://msdn.microsoft.com/en-us/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
