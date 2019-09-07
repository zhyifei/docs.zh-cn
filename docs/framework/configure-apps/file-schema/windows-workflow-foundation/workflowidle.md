---
title: <workflowIdle>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 1d8ddaf5d69d87ff6112b5cbb285f0ccfda724e2
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397540"
---
# <a name="workflowidle"></a><span data-ttu-id="c11cf-101">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="c11cf-101">\<workflowIdle></span></span>
<span data-ttu-id="c11cf-102">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="c11cf-102">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="c11cf-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c11cf-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c11cf-104">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c11cf-104">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="c11cf-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c11cf-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="c11cf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c11cf-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="c11cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="c11cf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="c11cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<workflowIdle >**</span><span class="sxs-lookup"><span data-stu-id="c11cf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<workflowIdle>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c11cf-109">语法</span><span class="sxs-lookup"><span data-stu-id="c11cf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c11cf-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c11cf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c11cf-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c11cf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c11cf-112">特性</span><span class="sxs-lookup"><span data-stu-id="c11cf-112">Attributes</span></span>  
  
|<span data-ttu-id="c11cf-113">特性</span><span class="sxs-lookup"><span data-stu-id="c11cf-113">Attribute</span></span>|<span data-ttu-id="c11cf-114">描述</span><span class="sxs-lookup"><span data-stu-id="c11cf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c11cf-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="c11cf-115">timeToPersist</span></span>|<span data-ttu-id="c11cf-116">一个 Timespan 值，该值指定工作流进入空闲状态与持久保存之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c11cf-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="c11cf-117">默认值为 Timespan.maxvalue。</span><span class="sxs-lookup"><span data-stu-id="c11cf-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="c11cf-118">该持续时间从工作流实例进入空闲状态时算起。</span><span class="sxs-lookup"><span data-stu-id="c11cf-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="c11cf-119">如果您想要更积极地持久保存工作流实例，同时还要尽可能长时间将实例保留在内存中，此属性非常有用。</span><span class="sxs-lookup"><span data-stu-id="c11cf-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="c11cf-120">仅当此属性的值小于**timeToUnload**属性时，此属性才有效。</span><span class="sxs-lookup"><span data-stu-id="c11cf-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="c11cf-121">如果大于该特性，将忽略此项。</span><span class="sxs-lookup"><span data-stu-id="c11cf-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="c11cf-122">如果此属性在**timeToUnload**属性指定的值之前过期，则必须在卸载工作流之前完成暂留。</span><span class="sxs-lookup"><span data-stu-id="c11cf-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="c11cf-123">这意味着卸载操作可能要等到工作流永久保留完毕才能进行。</span><span class="sxs-lookup"><span data-stu-id="c11cf-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="c11cf-124">永久层负责处理暂时性错误的任何重试操作，并仅在发生不可恢复的错误时引发异常。</span><span class="sxs-lookup"><span data-stu-id="c11cf-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="c11cf-125">因此，任何在持久性操作期间引发的异常都将被视为是致命的，并导致该工作流实例中止。</span><span class="sxs-lookup"><span data-stu-id="c11cf-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c11cf-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="c11cf-126">timeToUnload</span></span>|<span data-ttu-id="c11cf-127">一个 Timespan 值，该值指定工作流进入空闲状态与卸载工作流之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c11cf-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="c11cf-128">默认值为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="c11cf-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="c11cf-129">卸载一个工作流意味着该工作流已持久保存。</span><span class="sxs-lookup"><span data-stu-id="c11cf-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="c11cf-130">如果将此属性设置为零，则工作流实例将持久保存，并且在工作流进入空闲状态后立即将其卸载。</span><span class="sxs-lookup"><span data-stu-id="c11cf-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="c11cf-131">将此特性设置为 TimeSpan 会有效地禁用卸载操作。</span><span class="sxs-lookup"><span data-stu-id="c11cf-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="c11cf-132">处于空闲状态的工作流实例永远不会被卸载。</span><span class="sxs-lookup"><span data-stu-id="c11cf-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c11cf-133">子元素</span><span class="sxs-lookup"><span data-stu-id="c11cf-133">Child Elements</span></span>  
 <span data-ttu-id="c11cf-134">无。</span><span class="sxs-lookup"><span data-stu-id="c11cf-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c11cf-135">父元素</span><span class="sxs-lookup"><span data-stu-id="c11cf-135">Parent Elements</span></span>  
  
|<span data-ttu-id="c11cf-136">元素</span><span class="sxs-lookup"><span data-stu-id="c11cf-136">Element</span></span>|<span data-ttu-id="c11cf-137">描述</span><span class="sxs-lookup"><span data-stu-id="c11cf-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c11cf-138">\<serviceBehaviors > 的\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c11cf-138">\<behavior> of \<serviceBehaviors></span></span>](behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c11cf-139">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="c11cf-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c11cf-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="c11cf-140">See also</span></span>

- <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>
- <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
