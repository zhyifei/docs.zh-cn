---
title: <workflowUnhandledException>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: caf5be7aaff0df436be3a1d618a9f89bb32e6bb7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254842"
---
# <a name="workflowunhandledexception"></a><span data-ttu-id="a0535-101">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="a0535-101">\<workflowUnhandledException></span></span>
<span data-ttu-id="a0535-102">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="a0535-102">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="a0535-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="a0535-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="a0535-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="a0535-104">\<behaviors></span></span>  
<span data-ttu-id="a0535-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="a0535-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="a0535-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="a0535-106">\<behavior></span></span>  
<span data-ttu-id="a0535-107">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="a0535-107">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0535-108">语法</span><span class="sxs-lookup"><span data-stu-id="a0535-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0535-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a0535-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a0535-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a0535-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0535-111">特性</span><span class="sxs-lookup"><span data-stu-id="a0535-111">Attributes</span></span>  
  
|<span data-ttu-id="a0535-112">特性</span><span class="sxs-lookup"><span data-stu-id="a0535-112">Attribute</span></span>|<span data-ttu-id="a0535-113">描述</span><span class="sxs-lookup"><span data-stu-id="a0535-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a0535-114">action</span><span class="sxs-lookup"><span data-stu-id="a0535-114">action</span></span>|<span data-ttu-id="a0535-115">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="a0535-115">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="a0535-116">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="a0535-116">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a0535-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a0535-117">Child Elements</span></span>  
 <span data-ttu-id="a0535-118">无。</span><span class="sxs-lookup"><span data-stu-id="a0535-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a0535-119">父元素</span><span class="sxs-lookup"><span data-stu-id="a0535-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a0535-120">元素</span><span class="sxs-lookup"><span data-stu-id="a0535-120">Element</span></span>|<span data-ttu-id="a0535-121">描述</span><span class="sxs-lookup"><span data-stu-id="a0535-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0535-122">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="a0535-122">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="a0535-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="a0535-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0535-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0535-124">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
