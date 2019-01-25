---
title: '&lt;workflowUnhandledException&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 57adeab5-f06a-44b2-916b-0e177cf0f4a6
ms.openlocfilehash: 5c5dddc6d126811d7fd1eaae2f85df1e42c1cd41
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54700866"
---
# <a name="ltworkflowunhandledexceptiongt"></a><span data-ttu-id="f7223-102">&lt;workflowUnhandledException&gt;</span><span class="sxs-lookup"><span data-stu-id="f7223-102">&lt;workflowUnhandledException&gt;</span></span>
<span data-ttu-id="f7223-103">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="f7223-103">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>  
  
<span data-ttu-id="f7223-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="f7223-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f7223-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="f7223-105">\<behaviors></span></span>  
<span data-ttu-id="f7223-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="f7223-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="f7223-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="f7223-107">\<behavior></span></span>  
<span data-ttu-id="f7223-108">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="f7223-108">\<workflowUnhandledException></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7223-109">语法</span><span class="sxs-lookup"><span data-stu-id="f7223-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7223-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f7223-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f7223-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f7223-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7223-112">特性</span><span class="sxs-lookup"><span data-stu-id="f7223-112">Attributes</span></span>  
  
|<span data-ttu-id="f7223-113">特性</span><span class="sxs-lookup"><span data-stu-id="f7223-113">Attribute</span></span>|<span data-ttu-id="f7223-114">描述</span><span class="sxs-lookup"><span data-stu-id="f7223-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7223-115">action</span><span class="sxs-lookup"><span data-stu-id="f7223-115">action</span></span>|<span data-ttu-id="f7223-116">一个字符串，指定发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="f7223-116">A string that specifies the action to take when an unhandled exception occurs.</span></span> <span data-ttu-id="f7223-117">此特性的类型为 <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span><span class="sxs-lookup"><span data-stu-id="f7223-117">This attribute is of type <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionAction></span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7223-118">子元素</span><span class="sxs-lookup"><span data-stu-id="f7223-118">Child Elements</span></span>  
 <span data-ttu-id="f7223-119">无。</span><span class="sxs-lookup"><span data-stu-id="f7223-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7223-120">父元素</span><span class="sxs-lookup"><span data-stu-id="f7223-120">Parent Elements</span></span>  
  
|<span data-ttu-id="f7223-121">元素</span><span class="sxs-lookup"><span data-stu-id="f7223-121">Element</span></span>|<span data-ttu-id="f7223-122">描述</span><span class="sxs-lookup"><span data-stu-id="f7223-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7223-123">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="f7223-123">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="f7223-124">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="f7223-124">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f7223-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7223-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowUnhandledExceptionElement>
