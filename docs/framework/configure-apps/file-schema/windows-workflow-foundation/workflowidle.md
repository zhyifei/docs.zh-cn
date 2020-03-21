---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: d9eb182ef9c35d2e4c6f5d434e6b200ae2e7ca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151840"
---
# <a name="workflowidle"></a><span data-ttu-id="2391f-101">\<工作流 空闲></span><span class="sxs-lookup"><span data-stu-id="2391f-101">\<workflowIdle></span></span>
<span data-ttu-id="2391f-102">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="2391f-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="2391f-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2391f-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2391f-104">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2391f-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="2391f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2391f-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="2391f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务行为>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2391f-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="2391f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2391f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="2391f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<工作流 空闲>**</span><span class="sxs-lookup"><span data-stu-id="2391f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2391f-109">语法</span><span class="sxs-lookup"><span data-stu-id="2391f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2391f-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2391f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2391f-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2391f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2391f-112">属性</span><span class="sxs-lookup"><span data-stu-id="2391f-112">Attributes</span></span>  
  
|<span data-ttu-id="2391f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="2391f-113">Attribute</span></span>|<span data-ttu-id="2391f-114">说明</span><span class="sxs-lookup"><span data-stu-id="2391f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2391f-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="2391f-115">timeToPersist</span></span>|<span data-ttu-id="2391f-116">一个 Timespan 值，该值指定工作流进入空闲状态与持久保存工作流之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="2391f-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="2391f-117">默认值为 TimeSpan.MaxValue。</span><span class="sxs-lookup"><span data-stu-id="2391f-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="2391f-118">该持续时间从工作流实例进入空闲状态时算起。</span><span class="sxs-lookup"><span data-stu-id="2391f-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="2391f-119">如果您想要更积极地持久保存工作流实例，同时还要尽可能长久地在内存中保留该实例，此特性会非常有用。</span><span class="sxs-lookup"><span data-stu-id="2391f-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="2391f-120">仅当此属性的值小于**timeToUnload**属性时，此属性才有效。</span><span class="sxs-lookup"><span data-stu-id="2391f-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="2391f-121">如果大于该特性，将忽略此项。</span><span class="sxs-lookup"><span data-stu-id="2391f-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="2391f-122">如果此属性在**timeToUnload**属性指定的值之前经过，则在卸载工作流之前必须完成持久性。</span><span class="sxs-lookup"><span data-stu-id="2391f-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="2391f-123">这意味着卸载操作可能要等到工作流永久保留完毕才能进行。</span><span class="sxs-lookup"><span data-stu-id="2391f-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="2391f-124">永久层负责处理暂时性错误的任何重试操作，并仅在发生不可恢复的错误时引发异常。</span><span class="sxs-lookup"><span data-stu-id="2391f-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="2391f-125">因此，任何在持久性操作期间引发的异常都将被视为是致命的，并导致该工作流实例中止。</span><span class="sxs-lookup"><span data-stu-id="2391f-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="2391f-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="2391f-126">timeToUnload</span></span>|<span data-ttu-id="2391f-127">一个 Timespan 值，该值指定工作流进入空闲状态与卸载工作流之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="2391f-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="2391f-128">默认值为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="2391f-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="2391f-129">卸载一个工作流意味着该工作流已持久保存。</span><span class="sxs-lookup"><span data-stu-id="2391f-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="2391f-130">如果此特性设置为零，则在工作流进入空闲状态后会立即持久保存并卸载该工作流实例。</span><span class="sxs-lookup"><span data-stu-id="2391f-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="2391f-131">将此特性设置为 TimeSpan.MaxValue 可以有效地禁用卸载操作。</span><span class="sxs-lookup"><span data-stu-id="2391f-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="2391f-132">处于空闲状态的工作流实例永远不会被卸载。</span><span class="sxs-lookup"><span data-stu-id="2391f-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2391f-133">子元素</span><span class="sxs-lookup"><span data-stu-id="2391f-133">Child Elements</span></span>  
 <span data-ttu-id="2391f-134">无。</span><span class="sxs-lookup"><span data-stu-id="2391f-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2391f-135">父元素</span><span class="sxs-lookup"><span data-stu-id="2391f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="2391f-136">元素</span><span class="sxs-lookup"><span data-stu-id="2391f-136">Element</span></span>|<span data-ttu-id="2391f-137">说明</span><span class="sxs-lookup"><span data-stu-id="2391f-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2391f-138">\<服务行为行为\<>></span><span class="sxs-lookup"><span data-stu-id="2391f-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="2391f-139">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="2391f-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2391f-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2391f-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
