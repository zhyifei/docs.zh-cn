---
title: <add> 的 <commonParameters>
ms.date: 03/30/2017
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
ms.openlocfilehash: d682acd7fff6bab2c66660a028f8a75b780e21d2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400665"
---
# <a name="add-of-commonparameters"></a><span data-ttu-id="7aab3-102">\<添加 commonParameters > \<的 ></span><span class="sxs-lookup"><span data-stu-id="7aab3-102">\<add> of \<commonParameters></span></span>
<span data-ttu-id="7aab3-103">指定在多个服务之间全局使用的参数的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="7aab3-103">Specifies a name-value pair of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="7aab3-104">此参数通常包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7aab3-104">Typically this parameter includes the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="7aab3-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7aab3-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7aab3-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7aab3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7aab3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7aab3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowRuntime >** ](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="7aab3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<commonParameters >** ](commonparameters.md)</span><span class="sxs-lookup"><span data-stu-id="7aab3-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<commonParameters>**](commonparameters.md)</span></span>\
<span data-ttu-id="7aab3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="7aab3-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7aab3-113">语法</span><span class="sxs-lookup"><span data-stu-id="7aab3-113">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String" value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7aab3-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7aab3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="7aab3-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7aab3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7aab3-116">特性</span><span class="sxs-lookup"><span data-stu-id="7aab3-116">Attributes</span></span>  
  
|<span data-ttu-id="7aab3-117">特性</span><span class="sxs-lookup"><span data-stu-id="7aab3-117">Attribute</span></span>|<span data-ttu-id="7aab3-118">描述</span><span class="sxs-lookup"><span data-stu-id="7aab3-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7aab3-119">NAME</span><span class="sxs-lookup"><span data-stu-id="7aab3-119">name</span></span>|<span data-ttu-id="7aab3-120">为服务指定的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="7aab3-120">The name of the parameter specified for a service.</span></span>|  
|<span data-ttu-id="7aab3-121">值</span><span class="sxs-lookup"><span data-stu-id="7aab3-121">value</span></span>|<span data-ttu-id="7aab3-122">为服务指定的参数的值。</span><span class="sxs-lookup"><span data-stu-id="7aab3-122">The value of the parameter specified for a service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7aab3-123">子元素</span><span class="sxs-lookup"><span data-stu-id="7aab3-123">Child Elements</span></span>  
 <span data-ttu-id="7aab3-124">无。</span><span class="sxs-lookup"><span data-stu-id="7aab3-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7aab3-125">父元素</span><span class="sxs-lookup"><span data-stu-id="7aab3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7aab3-126">元素</span><span class="sxs-lookup"><span data-stu-id="7aab3-126">Element</span></span>|<span data-ttu-id="7aab3-127">描述</span><span class="sxs-lookup"><span data-stu-id="7aab3-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7aab3-128">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="7aab3-128">\<commonParameters></span></span>](commonparameters.md)|<span data-ttu-id="7aab3-129">服务使用的公用参数的集合。</span><span class="sxs-lookup"><span data-stu-id="7aab3-129">A collection of common parameters used by services.</span></span> <span data-ttu-id="7aab3-130">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="7aab3-130">This collection will typically include the database connection string that might be shared by durable services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7aab3-131">备注</span><span class="sxs-lookup"><span data-stu-id="7aab3-131">Remarks</span></span>  
 <span data-ttu-id="7aab3-132">`<commonParameters>` 元素定义在多个服务之间全局使用的任何参数，例如，使用 `ConnectionString` 时的<xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。</span><span class="sxs-lookup"><span data-stu-id="7aab3-132">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
 <span data-ttu-id="7aab3-133">对于提交批处理工作进行永久性存储的服务，如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 和 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>，可以通过使用 `EnableRetries` 参数来允许它们重试其事务，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="7aab3-133">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
    <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
         enableRetries="False" />
  </services>
</workflowRuntime>
```  
  
 <span data-ttu-id="7aab3-134">请注意， `EnableRetries`参数可以在全局级别（如*CommonParameters*部分所示）或支持`EnableRetries`的单个服务（如 "*服务*" 一节中所示）进行设置。</span><span class="sxs-lookup"><span data-stu-id="7aab3-134">Notice that the `EnableRetries` parameter can be set at either a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="7aab3-135">有关使用配置文件控制 Windows Workflow Foundation 主机应用程序的<xref:System.Workflow.Runtime.WorkflowRuntime>对象的行为的详细信息，请参阅[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="7aab3-135">For more information on using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aab3-136">示例</span><span class="sxs-lookup"><span data-stu-id="7aab3-136">Example</span></span>  
  
```xml  
<commonParameters>
  <add name="ConnectionString"
       value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
  <add name="EnableRetries"
       value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="7aab3-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="7aab3-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="7aab3-138">[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="7aab3-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="7aab3-139">\<commonParameters></span><span class="sxs-lookup"><span data-stu-id="7aab3-139">\<commonParameters></span></span>](commonparameters.md)
