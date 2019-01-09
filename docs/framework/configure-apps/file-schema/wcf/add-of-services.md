---
title: '&lt;services&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 9a86b7549e0efef10cbeb16dcc427d04065e43d3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145531"
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="ec380-102">&lt;services&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="ec380-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="ec380-103">指定的实例设置<xref:System.Workflow.Runtime.WorkflowRuntime>用于承载基于工作流的 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="ec380-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="ec380-104">此元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="ec380-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="ec380-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ec380-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec380-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ec380-106">\<behaviors></span></span>  
<span data-ttu-id="ec380-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="ec380-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="ec380-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="ec380-108">\<behavior></span></span>  
<span data-ttu-id="ec380-109">\<services></span><span class="sxs-lookup"><span data-stu-id="ec380-109">\<services></span></span>  
<span data-ttu-id="ec380-110">\<add></span><span class="sxs-lookup"><span data-stu-id="ec380-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec380-111">语法</span><span class="sxs-lookup"><span data-stu-id="ec380-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>
  <services>
    <add type="String" />
  </services>
</workflowRuntime>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec380-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ec380-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ec380-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ec380-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec380-114">特性</span><span class="sxs-lookup"><span data-stu-id="ec380-114">Attributes</span></span>  
  
|<span data-ttu-id="ec380-115">特性</span><span class="sxs-lookup"><span data-stu-id="ec380-115">Attribute</span></span>|<span data-ttu-id="ec380-116">描述</span><span class="sxs-lookup"><span data-stu-id="ec380-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec380-117">类型</span><span class="sxs-lookup"><span data-stu-id="ec380-117">type</span></span>|<span data-ttu-id="ec380-118">一个字符串，指定要进行初始化的服务的程序集限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="ec380-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="ec380-119">指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="ec380-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="ec380-120">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="ec380-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec380-121">子元素</span><span class="sxs-lookup"><span data-stu-id="ec380-121">Child Elements</span></span>  
 <span data-ttu-id="ec380-122">无。</span><span class="sxs-lookup"><span data-stu-id="ec380-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec380-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ec380-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ec380-124">元素</span><span class="sxs-lookup"><span data-stu-id="ec380-124">Element</span></span>|<span data-ttu-id="ec380-125">描述</span><span class="sxs-lookup"><span data-stu-id="ec380-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec380-126">\<services></span><span class="sxs-lookup"><span data-stu-id="ec380-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="ec380-127">将添加到 <xref:System.Workflow.Runtime.WorkflowRuntime> 引擎的服务的集合。</span><span class="sxs-lookup"><span data-stu-id="ec380-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="ec380-128">这些元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="ec380-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="ec380-129">在集合中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="ec380-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="ec380-130">因此，在集合中指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="ec380-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="ec380-131">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="ec380-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec380-132">备注</span><span class="sxs-lookup"><span data-stu-id="ec380-132">Remarks</span></span>  
 <span data-ttu-id="ec380-133">在此元素中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="ec380-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="ec380-134">因此，指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="ec380-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="ec380-135">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="ec380-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec380-136">示例</span><span class="sxs-lookup"><span data-stu-id="ec380-136">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ec380-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec380-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 <span data-ttu-id="ec380-138">[工作流配置文件](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ec380-138">[Workflow Configuration Files](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms732240(v=vs.90))</span></span>
