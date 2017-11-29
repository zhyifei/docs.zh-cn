---
title: "&lt;状态&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 73848bd1b8b23d6135572dc7fbb7b5e15b169554
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltstatesgt"></a><span data-ttu-id="efc26-102">&lt;状态&gt;</span><span class="sxs-lookup"><span data-stu-id="efc26-102">&lt;states&gt;</span></span>
<span data-ttu-id="efc26-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="efc26-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="efc26-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="efc26-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="efc26-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="efc26-105">\<system.serviceModel></span></span>  
<span data-ttu-id="efc26-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="efc26-106">\<tracking></span></span>  
<span data-ttu-id="efc26-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="efc26-107">\<trackingProfile></span></span>  
<span data-ttu-id="efc26-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="efc26-108">\<workflow></span></span>  
<span data-ttu-id="efc26-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="efc26-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="efc26-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="efc26-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="efc26-111">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="efc26-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc26-112">语法</span><span class="sxs-lookup"><span data-stu-id="efc26-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efc26-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="efc26-113">Attributes and Elements</span></span>  
 <span data-ttu-id="efc26-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="efc26-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efc26-115">特性</span><span class="sxs-lookup"><span data-stu-id="efc26-115">Attributes</span></span>  
 <span data-ttu-id="efc26-116">无。</span><span class="sxs-lookup"><span data-stu-id="efc26-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="efc26-117">子元素</span><span class="sxs-lookup"><span data-stu-id="efc26-117">Child Elements</span></span>  
  
|<span data-ttu-id="efc26-118">元素</span><span class="sxs-lookup"><span data-stu-id="efc26-118">Element</span></span>|<span data-ttu-id="efc26-119">描述</span><span class="sxs-lookup"><span data-stu-id="efc26-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efc26-120">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="efc26-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="efc26-121">创建跟踪记录时已跟踪工作流实例中的一个已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="efc26-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="efc26-122">父元素</span><span class="sxs-lookup"><span data-stu-id="efc26-122">Parent Elements</span></span>  
  
|<span data-ttu-id="efc26-123">元素</span><span class="sxs-lookup"><span data-stu-id="efc26-123">Element</span></span>|<span data-ttu-id="efc26-124">描述</span><span class="sxs-lookup"><span data-stu-id="efc26-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efc26-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="efc26-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="efc26-126">一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="efc26-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efc26-127">备注</span><span class="sxs-lookup"><span data-stu-id="efc26-127">Remarks</span></span>  
 <span data-ttu-id="efc26-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="efc26-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="efc26-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="efc26-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="efc26-130">状态</span><span class="sxs-lookup"><span data-stu-id="efc26-130">State</span></span>|<span data-ttu-id="efc26-131">描述</span><span class="sxs-lookup"><span data-stu-id="efc26-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="efc26-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="efc26-132">Aborted</span></span>|<span data-ttu-id="efc26-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="efc26-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="efc26-134">已完成</span><span class="sxs-lookup"><span data-stu-id="efc26-134">Completed</span></span>|<span data-ttu-id="efc26-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="efc26-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="efc26-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="efc26-136">Deleted</span></span>|<span data-ttu-id="efc26-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="efc26-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="efc26-138">Idle</span><span class="sxs-lookup"><span data-stu-id="efc26-138">Idle</span></span>|<span data-ttu-id="efc26-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="efc26-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="efc26-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="efc26-140">Persisted</span></span>|<span data-ttu-id="efc26-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="efc26-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="efc26-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="efc26-142">Resumed</span></span>|<span data-ttu-id="efc26-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="efc26-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="efc26-144">Started</span><span class="sxs-lookup"><span data-stu-id="efc26-144">Started</span></span>|<span data-ttu-id="efc26-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="efc26-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="efc26-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="efc26-146">UnhandledException</span></span>|<span data-ttu-id="efc26-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="efc26-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="efc26-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="efc26-148">Unloaded</span></span>|<span data-ttu-id="efc26-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="efc26-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="efc26-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="efc26-150">Canceled</span></span>|<span data-ttu-id="efc26-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="efc26-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="efc26-152">挂起</span><span class="sxs-lookup"><span data-stu-id="efc26-152">Suspended</span></span>|<span data-ttu-id="efc26-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="efc26-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="efc26-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="efc26-154">Terminated</span></span>|<span data-ttu-id="efc26-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="efc26-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="efc26-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="efc26-156">Unsuspended</span></span>|<span data-ttu-id="efc26-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="efc26-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="efc26-158">示例</span><span class="sxs-lookup"><span data-stu-id="efc26-158">Example</span></span>  
 <span data-ttu-id="efc26-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="efc26-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="efc26-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="efc26-160">See Also</span></span>  
 <span data-ttu-id="efc26-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="efc26-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="efc26-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="efc26-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="efc26-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="efc26-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="efc26-164">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="efc26-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="efc26-165">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="efc26-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
