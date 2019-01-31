---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: af8a2568eb13bb3007065c4b4a3564aae27de7ac
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280925"
---
# <a name="workflowidle"></a><span data-ttu-id="c4f47-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="c4f47-101">\<workflowIdle></span></span>
<span data-ttu-id="c4f47-102">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="c4f47-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="c4f47-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c4f47-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="c4f47-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="c4f47-104">\<behaviors></span></span>  
<span data-ttu-id="c4f47-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c4f47-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="c4f47-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c4f47-106">\<behavior></span></span>  
<span data-ttu-id="c4f47-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="c4f47-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f47-108">语法</span><span class="sxs-lookup"><span data-stu-id="c4f47-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <workflowIdle timeToPersist="TimeSpan" 
                    timeToUnload="TimeSpan" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4f47-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c4f47-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c4f47-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c4f47-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4f47-111">特性</span><span class="sxs-lookup"><span data-stu-id="c4f47-111">Attributes</span></span>  
  
|<span data-ttu-id="c4f47-112">特性</span><span class="sxs-lookup"><span data-stu-id="c4f47-112">Attribute</span></span>|<span data-ttu-id="c4f47-113">描述</span><span class="sxs-lookup"><span data-stu-id="c4f47-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4f47-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="c4f47-114">timeToPersist</span></span>|<span data-ttu-id="c4f47-115">一个 Timespan 值，该值指定工作流进入空闲状态并保持不变的时间之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c4f47-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="c4f47-116">默认值为 TimeSpan.MaxValue。</span><span class="sxs-lookup"><span data-stu-id="c4f47-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="c4f47-117">该持续时间从工作流实例进入空闲状态时算起。</span><span class="sxs-lookup"><span data-stu-id="c4f47-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="c4f47-118">此属性是很有用，如果你想要在内存中以尽可能长时间保持该实例的同时更主动的方式保留工作流实例。</span><span class="sxs-lookup"><span data-stu-id="c4f47-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="c4f47-119">此属性才有效，如果其值为小于**timeToUnload**属性。</span><span class="sxs-lookup"><span data-stu-id="c4f47-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="c4f47-120">如果大于该特性，将忽略此项。</span><span class="sxs-lookup"><span data-stu-id="c4f47-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="c4f47-121">如果此特性指定的值早**timeToUnload**持久性工作流在卸载之前必须完成的属性。</span><span class="sxs-lookup"><span data-stu-id="c4f47-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="c4f47-122">这意味着卸载操作可能要等到工作流永久保留完毕才能进行。</span><span class="sxs-lookup"><span data-stu-id="c4f47-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="c4f47-123">永久层负责处理暂时性错误的任何重试操作，并仅在发生不可恢复的错误时引发异常。</span><span class="sxs-lookup"><span data-stu-id="c4f47-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="c4f47-124">因此，任何在持久性操作期间引发的异常都将被视为是致命的，并导致该工作流实例中止。</span><span class="sxs-lookup"><span data-stu-id="c4f47-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c4f47-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="c4f47-125">timeToUnload</span></span>|<span data-ttu-id="c4f47-126">一个 Timespan 值，该值指定工作流进入空闲状态与卸载工作流之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c4f47-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="c4f47-127">默认值为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="c4f47-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="c4f47-128">卸载一个工作流意味着该工作流已持久保存。</span><span class="sxs-lookup"><span data-stu-id="c4f47-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="c4f47-129">如果此属性设置为零持久保存工作流实例并将其卸载后立即在工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c4f47-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="c4f47-130">此属性设置为 TimeSpan.MaxValue 有效地禁用卸载操作。</span><span class="sxs-lookup"><span data-stu-id="c4f47-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="c4f47-131">处于空闲状态的工作流实例永远不会被卸载。</span><span class="sxs-lookup"><span data-stu-id="c4f47-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4f47-132">子元素</span><span class="sxs-lookup"><span data-stu-id="c4f47-132">Child Elements</span></span>  
 <span data-ttu-id="c4f47-133">无。</span><span class="sxs-lookup"><span data-stu-id="c4f47-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4f47-134">父元素</span><span class="sxs-lookup"><span data-stu-id="c4f47-134">Parent Elements</span></span>  
  
|<span data-ttu-id="c4f47-135">元素</span><span class="sxs-lookup"><span data-stu-id="c4f47-135">Element</span></span>|<span data-ttu-id="c4f47-136">描述</span><span class="sxs-lookup"><span data-stu-id="c4f47-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4f47-137">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c4f47-137">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c4f47-138">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="c4f47-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4f47-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f47-139">See also</span></span>
- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
