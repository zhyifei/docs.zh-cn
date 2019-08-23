---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 16a485b6d0ba2584cccd08a36506582fd3930f71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947165"
---
# <a name="workflowidle"></a><span data-ttu-id="03613-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="03613-101">\<workflowIdle></span></span>
<span data-ttu-id="03613-102">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="03613-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="03613-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="03613-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="03613-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="03613-104">\<behaviors></span></span>  
<span data-ttu-id="03613-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="03613-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="03613-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="03613-106">\<behavior></span></span>  
<span data-ttu-id="03613-107">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="03613-107">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03613-108">语法</span><span class="sxs-lookup"><span data-stu-id="03613-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03613-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03613-109">Attributes and Elements</span></span>  
 <span data-ttu-id="03613-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03613-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03613-111">特性</span><span class="sxs-lookup"><span data-stu-id="03613-111">Attributes</span></span>  
  
|<span data-ttu-id="03613-112">特性</span><span class="sxs-lookup"><span data-stu-id="03613-112">Attribute</span></span>|<span data-ttu-id="03613-113">描述</span><span class="sxs-lookup"><span data-stu-id="03613-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03613-114">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="03613-114">timeToPersist</span></span>|<span data-ttu-id="03613-115">一个 Timespan 值, 该值指定工作流进入空闲状态与持久保存之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="03613-115">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="03613-116">默认值为 Timespan.maxvalue。</span><span class="sxs-lookup"><span data-stu-id="03613-116">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="03613-117">该持续时间从工作流实例进入空闲状态时算起。</span><span class="sxs-lookup"><span data-stu-id="03613-117">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="03613-118">如果您想要更积极地持久保存工作流实例, 同时还要尽可能长时间将实例保留在内存中, 此属性非常有用。</span><span class="sxs-lookup"><span data-stu-id="03613-118">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="03613-119">仅当此属性的值小于**timeToUnload**属性时, 此属性才有效。</span><span class="sxs-lookup"><span data-stu-id="03613-119">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="03613-120">如果大于该特性，将忽略此项。</span><span class="sxs-lookup"><span data-stu-id="03613-120">If it is greater, it is ignored.</span></span> <span data-ttu-id="03613-121">如果此属性在**timeToUnload**属性指定的值之前过期, 则必须在卸载工作流之前完成暂留。</span><span class="sxs-lookup"><span data-stu-id="03613-121">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="03613-122">这意味着卸载操作可能要等到工作流永久保留完毕才能进行。</span><span class="sxs-lookup"><span data-stu-id="03613-122">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="03613-123">永久层负责处理暂时性错误的任何重试操作，并仅在发生不可恢复的错误时引发异常。</span><span class="sxs-lookup"><span data-stu-id="03613-123">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="03613-124">因此，任何在持久性操作期间引发的异常都将被视为是致命的，并导致该工作流实例中止。</span><span class="sxs-lookup"><span data-stu-id="03613-124">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="03613-125">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="03613-125">timeToUnload</span></span>|<span data-ttu-id="03613-126">一个 Timespan 值，该值指定工作流进入空闲状态与卸载工作流之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="03613-126">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="03613-127">默认值为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="03613-127">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="03613-128">卸载一个工作流意味着该工作流已持久保存。</span><span class="sxs-lookup"><span data-stu-id="03613-128">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="03613-129">如果将此属性设置为零, 则工作流实例将持久保存, 并且在工作流进入空闲状态后立即将其卸载。</span><span class="sxs-lookup"><span data-stu-id="03613-129">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="03613-130">将此特性设置为 TimeSpan 会有效地禁用卸载操作。</span><span class="sxs-lookup"><span data-stu-id="03613-130">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="03613-131">处于空闲状态的工作流实例永远不会被卸载。</span><span class="sxs-lookup"><span data-stu-id="03613-131">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03613-132">子元素</span><span class="sxs-lookup"><span data-stu-id="03613-132">Child Elements</span></span>  
 <span data-ttu-id="03613-133">无。</span><span class="sxs-lookup"><span data-stu-id="03613-133">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03613-134">父元素</span><span class="sxs-lookup"><span data-stu-id="03613-134">Parent Elements</span></span>  
  
|<span data-ttu-id="03613-135">元素</span><span class="sxs-lookup"><span data-stu-id="03613-135">Element</span></span>|<span data-ttu-id="03613-136">描述</span><span class="sxs-lookup"><span data-stu-id="03613-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03613-137">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="03613-137">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="03613-138">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="03613-138">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03613-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="03613-139">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
