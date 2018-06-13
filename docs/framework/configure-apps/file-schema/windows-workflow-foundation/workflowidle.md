---
title: '&lt;workflowIdle&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b2ef703c-3e01-4213-9d2e-c14c7dba94d2
ms.openlocfilehash: 65bcc1ccd357fb7f331665aefbd975b11a2378cd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756899"
---
# <a name="ltworkflowidlegt"></a><span data-ttu-id="c3731-102">&lt;workflowIdle&gt;</span><span class="sxs-lookup"><span data-stu-id="c3731-102">&lt;workflowIdle&gt;</span></span>
<span data-ttu-id="c3731-103">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="c3731-103">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>  
  
<span data-ttu-id="c3731-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c3731-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c3731-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c3731-105">\<behaviors></span></span>  
<span data-ttu-id="c3731-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="c3731-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c3731-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c3731-107">\<behavior></span></span>  
<span data-ttu-id="c3731-108">\<workflowIdle ></span><span class="sxs-lookup"><span data-stu-id="c3731-108">\<workflowIdle></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3731-109">语法</span><span class="sxs-lookup"><span data-stu-id="c3731-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3731-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c3731-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c3731-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c3731-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3731-112">特性</span><span class="sxs-lookup"><span data-stu-id="c3731-112">Attributes</span></span>  
  
|<span data-ttu-id="c3731-113">特性</span><span class="sxs-lookup"><span data-stu-id="c3731-113">Attribute</span></span>|<span data-ttu-id="c3731-114">描述</span><span class="sxs-lookup"><span data-stu-id="c3731-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c3731-115">timeToPersist</span><span class="sxs-lookup"><span data-stu-id="c3731-115">timeToPersist</span></span>|<span data-ttu-id="c3731-116">一个 Timespan 值，指定工作流进入空闲状态到变为保留的时间之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c3731-116">A Timespan value that specifies the duration between the time the workflow becomes idle and is persisted.</span></span> <span data-ttu-id="c3731-117">默认值为 TimeSpan.MaxValue。</span><span class="sxs-lookup"><span data-stu-id="c3731-117">The default value is TimeSpan.MaxValue.</span></span><br /><br /> <span data-ttu-id="c3731-118">该持续时间从工作流实例进入空闲状态时算起。</span><span class="sxs-lookup"><span data-stu-id="c3731-118">The duration begins to elapse when the workflow instance becomes idle.</span></span> <span data-ttu-id="c3731-119">此属性是你想要同时为尽可能长时间在内存中保留实例更加主动地保留工作流实例的情况下很有用。</span><span class="sxs-lookup"><span data-stu-id="c3731-119">This attribute  is useful if you want to persist a workflow instance more aggressively while still keeping the instance in memory for as long as possible.</span></span> <span data-ttu-id="c3731-120">此属性才有效，其值是否小于**timeToUnload**属性。</span><span class="sxs-lookup"><span data-stu-id="c3731-120">This attribute  is only valid if its value is less than the **timeToUnload** attribute.</span></span> <span data-ttu-id="c3731-121">如果大于该特性，将忽略此项。</span><span class="sxs-lookup"><span data-stu-id="c3731-121">If it is greater, it is ignored.</span></span> <span data-ttu-id="c3731-122">如果此属性之前指定的值经过**timeToUnload**持久性工作流被卸载前必须完成的属性。</span><span class="sxs-lookup"><span data-stu-id="c3731-122">If this attribute elapses before the value specified by the **timeToUnload** attribute, persistence must complete before the workflow is unloaded.</span></span> <span data-ttu-id="c3731-123">这意味着卸载操作可能要等到工作流永久保留完毕才能进行。</span><span class="sxs-lookup"><span data-stu-id="c3731-123">This implies that the unload operation may be delayed until the workflow is persisted.</span></span> <span data-ttu-id="c3731-124">永久层负责处理暂时性错误的任何重试操作，并仅在发生不可恢复的错误时引发异常。</span><span class="sxs-lookup"><span data-stu-id="c3731-124">The persistence layer is responsible for handling any retries for transient errors and only throws exceptions on non-recoverable errors.</span></span> <span data-ttu-id="c3731-125">因此，任何在持久性操作期间引发的异常都将被视为是致命的，并导致该工作流实例中止。</span><span class="sxs-lookup"><span data-stu-id="c3731-125">Therefore, any exceptions thrown during persistence are treated as fatal and the workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c3731-126">timeToUnload</span><span class="sxs-lookup"><span data-stu-id="c3731-126">timeToUnload</span></span>|<span data-ttu-id="c3731-127">一个 Timespan 值，该值指定工作流进入空闲状态与卸载工作流之间的持续时间。</span><span class="sxs-lookup"><span data-stu-id="c3731-127">A Timespan value that specifies the duration between the time the workflow becomes idle and is unloaded.</span></span> <span data-ttu-id="c3731-128">默认值为 1 分钟。</span><span class="sxs-lookup"><span data-stu-id="c3731-128">The default value is 1 minute.</span></span><br /><br /> <span data-ttu-id="c3731-129">卸载一个工作流意味着该工作流已持久保存。</span><span class="sxs-lookup"><span data-stu-id="c3731-129">Unloading a workflow implies that it is also persisted.</span></span> <span data-ttu-id="c3731-130">如果此属性设置为零持久保存工作流实例，并后立即卸载工作流进入空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c3731-130">If this attribute is set to zero the workflow instance is persisted and unloaded immediately after the workflow becomes idle.</span></span> <span data-ttu-id="c3731-131">此属性设置为 TimeSpan.MaxValue 有效禁用卸载操作。</span><span class="sxs-lookup"><span data-stu-id="c3731-131">Setting this attribute to TimeSpan.MaxValue effectively disables the unload operation.</span></span> <span data-ttu-id="c3731-132">处于空闲状态的工作流实例永远不会被卸载。</span><span class="sxs-lookup"><span data-stu-id="c3731-132">Idle workflow instances are never unloaded.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3731-133">子元素</span><span class="sxs-lookup"><span data-stu-id="c3731-133">Child Elements</span></span>  
 <span data-ttu-id="c3731-134">无。</span><span class="sxs-lookup"><span data-stu-id="c3731-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3731-135">父元素</span><span class="sxs-lookup"><span data-stu-id="c3731-135">Parent Elements</span></span>  
  
|<span data-ttu-id="c3731-136">元素</span><span class="sxs-lookup"><span data-stu-id="c3731-136">Element</span></span>|<span data-ttu-id="c3731-137">描述</span><span class="sxs-lookup"><span data-stu-id="c3731-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c3731-138">\<行为 > 的\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c3731-138">\<behavior> of \<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|<span data-ttu-id="c3731-139">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="c3731-139">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c3731-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3731-140">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>  
 <xref:System.ServiceModel.Activities.Configuration.WorkflowIdleElement>
