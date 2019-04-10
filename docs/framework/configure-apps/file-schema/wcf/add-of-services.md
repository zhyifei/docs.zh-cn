---
title: <add> 的 <services>
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: c07b3377db4f5b434fd021b09de510c1d43ec832
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219182"
---
# <a name="add-of-services"></a><span data-ttu-id="8650e-102">\<add> of \<services></span><span class="sxs-lookup"><span data-stu-id="8650e-102">\<add> of \<services></span></span>
<span data-ttu-id="8650e-103">指定的实例设置<xref:System.Workflow.Runtime.WorkflowRuntime>用于承载基于工作流的 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="8650e-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="8650e-104">此元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="8650e-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="8650e-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="8650e-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="8650e-106">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="8650e-106">\<behaviors></span></span>  
<span data-ttu-id="8650e-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="8650e-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="8650e-108">\<behavior></span><span class="sxs-lookup"><span data-stu-id="8650e-108">\<behavior></span></span>  
<span data-ttu-id="8650e-109">\<services></span><span class="sxs-lookup"><span data-stu-id="8650e-109">\<services></span></span>  
<span data-ttu-id="8650e-110">\<add></span><span class="sxs-lookup"><span data-stu-id="8650e-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8650e-111">语法</span><span class="sxs-lookup"><span data-stu-id="8650e-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8650e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8650e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8650e-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8650e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8650e-114">特性</span><span class="sxs-lookup"><span data-stu-id="8650e-114">Attributes</span></span>  
  
|<span data-ttu-id="8650e-115">特性</span><span class="sxs-lookup"><span data-stu-id="8650e-115">Attribute</span></span>|<span data-ttu-id="8650e-116">描述</span><span class="sxs-lookup"><span data-stu-id="8650e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8650e-117">类型</span><span class="sxs-lookup"><span data-stu-id="8650e-117">type</span></span>|<span data-ttu-id="8650e-118">一个字符串，指定要进行初始化的服务的程序集限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="8650e-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="8650e-119">指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="8650e-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="8650e-120">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="8650e-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8650e-121">子元素</span><span class="sxs-lookup"><span data-stu-id="8650e-121">Child Elements</span></span>  
 <span data-ttu-id="8650e-122">无。</span><span class="sxs-lookup"><span data-stu-id="8650e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8650e-123">父元素</span><span class="sxs-lookup"><span data-stu-id="8650e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8650e-124">元素</span><span class="sxs-lookup"><span data-stu-id="8650e-124">Element</span></span>|<span data-ttu-id="8650e-125">描述</span><span class="sxs-lookup"><span data-stu-id="8650e-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8650e-126">\<services></span><span class="sxs-lookup"><span data-stu-id="8650e-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="8650e-127">将添加到 <xref:System.Workflow.Runtime.WorkflowRuntime> 引擎的服务的集合。</span><span class="sxs-lookup"><span data-stu-id="8650e-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="8650e-128">这些元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="8650e-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="8650e-129">在集合中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="8650e-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="8650e-130">因此，在集合中指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="8650e-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="8650e-131">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="8650e-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8650e-132">备注</span><span class="sxs-lookup"><span data-stu-id="8650e-132">Remarks</span></span>  
 <span data-ttu-id="8650e-133">在此元素中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="8650e-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="8650e-134">因此，指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="8650e-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="8650e-135">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="8650e-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8650e-136">示例</span><span class="sxs-lookup"><span data-stu-id="8650e-136">Example</span></span>  
  
```xml  
<serviceBehaviors>
  <behavior name="ServiceBehavior">
    <workflowRuntime name="WorkflowServiceHostRuntime"
                     validateOnCreate="true"
                     enablePerformanceCounters="true">
      <services>
        <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common" />
      </services>
    </workflowRuntime>
  </behavior>
</serviceBehaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="8650e-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="8650e-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>
- <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>
- <xref:System.Workflow.Runtime.WorkflowRuntime>
- [<span data-ttu-id="8650e-138">工作流配置文件</span><span class="sxs-lookup"><span data-stu-id="8650e-138">Workflow Configuration Files</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))
