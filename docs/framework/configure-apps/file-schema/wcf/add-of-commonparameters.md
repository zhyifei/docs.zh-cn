---
title: '&lt;commonParameters&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: 93e82aa3bd44a747d1e85986c51c21522d709bd0
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489846"
---
# <a name="ltaddgt-of-ltcommonparametersgt"></a><span data-ttu-id="56e50-102">&lt;commonParameters&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="56e50-102">&lt;add&gt; of &lt;commonParameters&gt;</span></span>
<span data-ttu-id="56e50-103">指定在多个服务之间全局使用的参数的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="56e50-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="56e50-104">此参数通常包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="56e50-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
 <span data-ttu-id="56e50-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="56e50-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="56e50-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="56e50-106">\<behaviors></span></span>  
<span data-ttu-id="56e50-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="56e50-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="56e50-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="56e50-108">\<behavior></span></span>  
<span data-ttu-id="56e50-109">\<workflowRuntime></span><span class="sxs-lookup"><span data-stu-id="56e50-109">\<workflowRuntime></span></span>  
<span data-ttu-id="56e50-110">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="56e50-110">\<commonParameters></span></span>  
<span data-ttu-id="56e50-111">\<add></span><span class="sxs-lookup"><span data-stu-id="56e50-111">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e50-112">语法</span><span class="sxs-lookup"><span data-stu-id="56e50-112">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="56e50-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="56e50-113">Attributes and Elements</span></span>  
 <span data-ttu-id="56e50-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="56e50-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="56e50-115">特性</span><span class="sxs-lookup"><span data-stu-id="56e50-115">Attributes</span></span>  
  
|<span data-ttu-id="56e50-116">特性</span><span class="sxs-lookup"><span data-stu-id="56e50-116">Attribute</span></span>|<span data-ttu-id="56e50-117">描述</span><span class="sxs-lookup"><span data-stu-id="56e50-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="56e50-118">name</span><span class="sxs-lookup"><span data-stu-id="56e50-118">name</span></span>|<span data-ttu-id="56e50-119">为服务指定的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="56e50-119">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="56e50-120">值</span><span class="sxs-lookup"><span data-stu-id="56e50-120">value</span></span>|<span data-ttu-id="56e50-121">为服务指定的参数的值。</span><span class="sxs-lookup"><span data-stu-id="56e50-121">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="56e50-122">子元素</span><span class="sxs-lookup"><span data-stu-id="56e50-122">Child Elements</span></span>  
 <span data-ttu-id="56e50-123">无。</span><span class="sxs-lookup"><span data-stu-id="56e50-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="56e50-124">父元素</span><span class="sxs-lookup"><span data-stu-id="56e50-124">Parent Elements</span></span>  
  
|<span data-ttu-id="56e50-125">元素</span><span class="sxs-lookup"><span data-stu-id="56e50-125">Element</span></span>|<span data-ttu-id="56e50-126">描述</span><span class="sxs-lookup"><span data-stu-id="56e50-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="56e50-127">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="56e50-127">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|<span data-ttu-id="56e50-128">服务使用的公用参数的集合。</span><span class="sxs-lookup"><span data-stu-id="56e50-128">A collection of common parameters used by services.</span></span> <span data-ttu-id="56e50-129">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="56e50-129">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56e50-130">备注</span><span class="sxs-lookup"><span data-stu-id="56e50-130">Remarks</span></span>  
 <span data-ttu-id="56e50-131">`<commonParameters>` 元素定义在多个服务之间全局使用的任何参数，例如，使用 `ConnectionString` 时的<xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。</span><span class="sxs-lookup"><span data-stu-id="56e50-131">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="56e50-132">对于提交批处理工作进行永久性存储的服务，如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 和 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>，可以通过使用 `EnableRetries` 参数来允许它们重试其事务，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="56e50-132">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="56e50-133">请注意，`EnableRetries`参数可设置为在全局级别 (如中所示*CommonParameters*部分) 或为个别支持的服务`EnableRetries`(如中所示*服务*部分)。</span><span class="sxs-lookup"><span data-stu-id="56e50-133">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="56e50-134">有关使用配置文件来控制行为的详细信息<xref:System.Workflow.Runtime.WorkflowRuntime>对象的 Windows Workflow Foundation 主机应用程序，请参阅[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="56e50-134">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e50-135">示例</span><span class="sxs-lookup"><span data-stu-id="56e50-135">Example</span></span>  
  
```xml  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56e50-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="56e50-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>  
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>  
 <span data-ttu-id="56e50-137">[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="56e50-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>  
 [<span data-ttu-id="56e50-138">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="56e50-138">\<commonParameters></span></span>](https://msdn.microsoft.com/library/d0e1e6fc-985a-4713-b7da-194e30dfab4c)
