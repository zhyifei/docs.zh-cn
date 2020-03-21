---
title: <commonParameters>
ms.date: 03/30/2017
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
ms.openlocfilehash: 73d8549f68e8ca77115619431c857c4a2aac3fdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153017"
---
# <a name="commonparameters"></a><span data-ttu-id="6ea72-101">\<共同参数></span><span class="sxs-lookup"><span data-stu-id="6ea72-101">\<commonParameters></span></span>
<span data-ttu-id="6ea72-102">表示在多个服务之间全局使用的参数的集合。</span><span class="sxs-lookup"><span data-stu-id="6ea72-102">Represents a collection of parameters that are used globally across multiple services.</span></span> <span data-ttu-id="6ea72-103">此集合通常将包括可由持久性服务共享的数据库连接字符串。</span><span class="sxs-lookup"><span data-stu-id="6ea72-103">This collection will typically include the database connection string that might be shared by durable services.</span></span>  
  
<span data-ttu-id="6ea72-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6ea72-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6ea72-105">&nbsp;&nbsp;[**\<系统.服务模式>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6ea72-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6ea72-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ea72-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="6ea72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务行为>**](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ea72-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="6ea72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ea72-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="6ea72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流运行时>**](workflowruntime.md)</span><span class="sxs-lookup"><span data-stu-id="6ea72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowRuntime>**](workflowruntime.md)</span></span>\
<span data-ttu-id="6ea72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<公共参数>**</span><span class="sxs-lookup"><span data-stu-id="6ea72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<commonParameters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ea72-111">语法</span><span class="sxs-lookup"><span data-stu-id="6ea72-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <commonParameters>
    <add name="String"
         value="String" />
  </commonParameters>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6ea72-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6ea72-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6ea72-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6ea72-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6ea72-114">属性</span><span class="sxs-lookup"><span data-stu-id="6ea72-114">Attributes</span></span>  
 <span data-ttu-id="6ea72-115">无。</span><span class="sxs-lookup"><span data-stu-id="6ea72-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6ea72-116">子元素</span><span class="sxs-lookup"><span data-stu-id="6ea72-116">Child Elements</span></span>  
  
|<span data-ttu-id="6ea72-117">元素</span><span class="sxs-lookup"><span data-stu-id="6ea72-117">Element</span></span>|<span data-ttu-id="6ea72-118">说明</span><span class="sxs-lookup"><span data-stu-id="6ea72-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ea72-119">\<添加></span><span class="sxs-lookup"><span data-stu-id="6ea72-119">\<add></span></span>](add-of-commonparameters.md)|<span data-ttu-id="6ea72-120">将服务使用的公共参数的名称/值对添加到集合。</span><span class="sxs-lookup"><span data-stu-id="6ea72-120">Adds a name-value pair of common parameters used by services to the collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6ea72-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6ea72-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6ea72-122">元素</span><span class="sxs-lookup"><span data-stu-id="6ea72-122">Element</span></span>|<span data-ttu-id="6ea72-123">说明</span><span class="sxs-lookup"><span data-stu-id="6ea72-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6ea72-124">\<工作流运行时></span><span class="sxs-lookup"><span data-stu-id="6ea72-124">\<workflowRuntime></span></span>](workflowruntime.md)|<span data-ttu-id="6ea72-125">指定<xref:System.Workflow.Runtime.WorkflowRuntime>托管基于工作流的 Windows 通信基础 （WCF） 服务的实例的设置。</span><span class="sxs-lookup"><span data-stu-id="6ea72-125">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ea72-126">备注</span><span class="sxs-lookup"><span data-stu-id="6ea72-126">Remarks</span></span>  
 <span data-ttu-id="6ea72-127">`<commonParameters>` 元素定义在多个服务之间全局使用的任何参数，例如，使用 `ConnectionString` 时的<xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>。</span><span class="sxs-lookup"><span data-stu-id="6ea72-127">The `<commonParameters>` element defines any parameters that are used globally across multiple services, for example `ConnectionString` when using the <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ea72-128">如果在 `ConnectionString` 一节中指定了 `<commonParameters>` 值，则 SQL Tracking 服务并不始终使用该值。</span><span class="sxs-lookup"><span data-stu-id="6ea72-128">SQL Tracking service does not consistently use the `ConnectionString` value if it is specified in the `<commonParameters>` section.</span></span> <span data-ttu-id="6ea72-129">它的某些操作可能会失败，例如检索 `StateMachineWorkflowInstance.StateHistory` 属性。</span><span class="sxs-lookup"><span data-stu-id="6ea72-129">Some of its operations such as retrieving the `StateMachineWorkflowInstance.StateHistory` property may fail.</span></span> <span data-ttu-id="6ea72-130">若要解决此问题，请在跟踪提供程序的配置节指定 `ConnectionString` 属性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6ea72-130">To workaround this, specify the `ConnectionString` attribute in the configuration section for tracking provider, as indicated in the following example.</span></span>  

```xml  
<add
type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />
```  
  
 <span data-ttu-id="6ea72-131">对于提交批处理工作进行永久性存储的服务，如 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 和 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>，可以通过使用 `EnableRetries` 参数来允许它们重试其事务，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="6ea72-131">For services that commit work batches to persistence stores, such as <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> and <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, you can enable them to retry their transaction by using the `EnableRetries` parameter as shown in the following example:</span></span>  
  
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
  
 <span data-ttu-id="6ea72-132">请注意，`EnableRetries`参数可以在全局级别设置（如 *"通用参数*"部分所示），也可以设置支持`EnableRetries`的各个服务（如 *"服务*"部分所示）。</span><span class="sxs-lookup"><span data-stu-id="6ea72-132">Notice that the `EnableRetries` parameter can be set either at a global level (as shown in the *CommonParameters* section) or for individual services that support `EnableRetries` (as shown in the *Services* section).</span></span>  
  
 <span data-ttu-id="6ea72-133">以下示例代码演示如何以编程方式更改公共参数：</span><span class="sxs-lookup"><span data-stu-id="6ea72-133">The following sample code shows how to change the common parameters programmatically:</span></span>
  
```csharp  
Configuration config = WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");
var wfruntime = config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters = wfruntime.CommonParameters;
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 <span data-ttu-id="6ea72-134">有关使用配置文件控制 Windows 工作流基础主机应用程序<xref:System.Workflow.Runtime.WorkflowRuntime>对象的行为的详细信息，请参阅[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))。</span><span class="sxs-lookup"><span data-stu-id="6ea72-134">For more information about using a configuration file to control the behavior of a <xref:System.Workflow.Runtime.WorkflowRuntime> object of a Windows Workflow Foundation host application, see [Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ea72-135">示例</span><span class="sxs-lookup"><span data-stu-id="6ea72-135">Example</span></span>  
  
```xml  
<commonParameters>
   <add name="ConnectionString"
        value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />
   <add name="EnableRetries"
        value="true" />
</commonParameters>
```  
  
## <a name="see-also"></a><span data-ttu-id="6ea72-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea72-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>
- <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>
- <span data-ttu-id="6ea72-137">[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="6ea72-137">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
- [<span data-ttu-id="6ea72-138">\<添加></span><span class="sxs-lookup"><span data-stu-id="6ea72-138">\<add></span></span>](add-of-commonparameters.md)
