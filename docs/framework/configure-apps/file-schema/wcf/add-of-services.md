---
title: '&lt;services&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
ms.openlocfilehash: 709636f0b9667a431838b463c05cfd00f6521f6b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltservicesgt"></a><span data-ttu-id="9e10f-102">&lt;services&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="9e10f-102">&lt;add&gt; of &lt;services&gt;</span></span>
<span data-ttu-id="9e10f-103">指定的实例的设置<xref:System.Workflow.Runtime.WorkflowRuntime>用于承载基于工作流的 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="9e10f-103">Specifies settings for an instance of <xref:System.Workflow.Runtime.WorkflowRuntime> for hosting workflow-based Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="9e10f-104">此元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9e10f-104">This element is of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  
  
 <span data-ttu-id="9e10f-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9e10f-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9e10f-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9e10f-106">\<behaviors></span></span>  
<span data-ttu-id="9e10f-107">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="9e10f-107">\<serviceBehaviors></span></span>  
<span data-ttu-id="9e10f-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="9e10f-108">\<behavior></span></span>  
<span data-ttu-id="9e10f-109">\<services></span><span class="sxs-lookup"><span data-stu-id="9e10f-109">\<services></span></span>  
<span data-ttu-id="9e10f-110">\<add></span><span class="sxs-lookup"><span data-stu-id="9e10f-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e10f-111">语法</span><span class="sxs-lookup"><span data-stu-id="9e10f-111">Syntax</span></span>  
  
```xml  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e10f-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9e10f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9e10f-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9e10f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e10f-114">特性</span><span class="sxs-lookup"><span data-stu-id="9e10f-114">Attributes</span></span>  
  
|<span data-ttu-id="9e10f-115">特性</span><span class="sxs-lookup"><span data-stu-id="9e10f-115">Attribute</span></span>|<span data-ttu-id="9e10f-116">描述</span><span class="sxs-lookup"><span data-stu-id="9e10f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e10f-117">类型</span><span class="sxs-lookup"><span data-stu-id="9e10f-117">type</span></span>|<span data-ttu-id="9e10f-118">一个字符串，指定要进行初始化的服务的程序集限定类型名称。</span><span class="sxs-lookup"><span data-stu-id="9e10f-118">A string that specifies the assembly-qualified type name of the service to be initialized.</span></span> <span data-ttu-id="9e10f-119">指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="9e10f-119">The service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="9e10f-120">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9e10f-120">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e10f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="9e10f-121">Child Elements</span></span>  
 <span data-ttu-id="9e10f-122">无。</span><span class="sxs-lookup"><span data-stu-id="9e10f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e10f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="9e10f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9e10f-124">元素</span><span class="sxs-lookup"><span data-stu-id="9e10f-124">Element</span></span>|<span data-ttu-id="9e10f-125">描述</span><span class="sxs-lookup"><span data-stu-id="9e10f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e10f-126">\<services></span><span class="sxs-lookup"><span data-stu-id="9e10f-126">\<services></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|<span data-ttu-id="9e10f-127">将添加到 <xref:System.Workflow.Runtime.WorkflowRuntime> 引擎的服务的集合。</span><span class="sxs-lookup"><span data-stu-id="9e10f-127">A collection of services that will be added to the <xref:System.Workflow.Runtime.WorkflowRuntime> engine.</span></span> <span data-ttu-id="9e10f-128">这些元素的类型为 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9e10f-128">The elements are of type <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.</span></span>  <span data-ttu-id="9e10f-129">在集合中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="9e10f-129">The services specified in the collection will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="9e10f-130">因此，在集合中指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="9e10f-130">Therefore, the services specified in the collection must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="9e10f-131">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9e10f-131">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e10f-132">备注</span><span class="sxs-lookup"><span data-stu-id="9e10f-132">Remarks</span></span>  
 <span data-ttu-id="9e10f-133">在此元素中指定的服务将由工作流运行时引擎初始化，并在调用适当的 <xref:System.Workflow.Runtime.WorkflowRuntime> 构造函数时添加到工作流运行时引擎服务中。</span><span class="sxs-lookup"><span data-stu-id="9e10f-133">The service specified in this element will be initialized by the workflow runtime engine and added to its services when the appropriate <xref:System.Workflow.Runtime.WorkflowRuntime> constructor is called.</span></span> <span data-ttu-id="9e10f-134">因此，指定的服务必须遵循关于其构造函数的签名的某些规则。</span><span class="sxs-lookup"><span data-stu-id="9e10f-134">Therefore, the service specified must follow certain rules about the signatures of their constructors.</span></span> <span data-ttu-id="9e10f-135">有关更多信息，请参见<xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>。</span><span class="sxs-lookup"><span data-stu-id="9e10f-135">See <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement> for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e10f-136">示例</span><span class="sxs-lookup"><span data-stu-id="9e10f-136">Example</span></span>  
  
```xml  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e10f-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e10f-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>  
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>  
 <xref:System.Workflow.Runtime.WorkflowRuntime>  
 [<span data-ttu-id="9e10f-138">工作流配置文件</span><span class="sxs-lookup"><span data-stu-id="9e10f-138">Workflow Configuration Files</span></span>](http://msdn.microsoft.com/library/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)
