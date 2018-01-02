---
title: "WCF 的 &lt;states&gt;，&lt;workflowInstanceQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5995ebfc2cee0f636d2acd8b1cadead0bc7b67e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="c4780-102">WCF 的 &lt;states&gt;，&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="c4780-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>
<span data-ttu-id="c4780-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="c4780-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="c4780-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c4780-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="c4780-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="c4780-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c4780-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="c4780-106">\<tracking></span></span>  
<span data-ttu-id="c4780-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="c4780-107">\<trackingProfile></span></span>  
<span data-ttu-id="c4780-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="c4780-108">\<workflow></span></span>  
<span data-ttu-id="c4780-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="c4780-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="c4780-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="c4780-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="c4780-111">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="c4780-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4780-112">语法</span><span class="sxs-lookup"><span data-stu-id="c4780-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <workflowInstanceQueries>             <workflowInstanceQuery>                <states>                   <state name="Name"/>                </states>            </workflowInstanceQuery>         </workflowInstanceQueries>       </workflow>   </trackingProfile></tracking>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4780-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c4780-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c4780-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c4780-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4780-115">特性</span><span class="sxs-lookup"><span data-stu-id="c4780-115">Attributes</span></span>  
 <span data-ttu-id="c4780-116">无。</span><span class="sxs-lookup"><span data-stu-id="c4780-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c4780-117">子元素</span><span class="sxs-lookup"><span data-stu-id="c4780-117">Child Elements</span></span>  
  
|<span data-ttu-id="c4780-118">元素</span><span class="sxs-lookup"><span data-stu-id="c4780-118">Element</span></span>|<span data-ttu-id="c4780-119">描述</span><span class="sxs-lookup"><span data-stu-id="c4780-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4780-120">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="c4780-120">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="c4780-121">创建跟踪记录时已跟踪工作流实例中的一个已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="c4780-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c4780-122">父元素</span><span class="sxs-lookup"><span data-stu-id="c4780-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c4780-123">元素</span><span class="sxs-lookup"><span data-stu-id="c4780-123">Element</span></span>|<span data-ttu-id="c4780-124">描述</span><span class="sxs-lookup"><span data-stu-id="c4780-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4780-125">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="c4780-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="c4780-126">一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="c4780-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4780-127">备注</span><span class="sxs-lookup"><span data-stu-id="c4780-127">Remarks</span></span>  
 <span data-ttu-id="c4780-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="c4780-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="c4780-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="c4780-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="c4780-130">状态</span><span class="sxs-lookup"><span data-stu-id="c4780-130">State</span></span>|<span data-ttu-id="c4780-131">描述</span><span class="sxs-lookup"><span data-stu-id="c4780-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4780-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="c4780-132">Aborted</span></span>|<span data-ttu-id="c4780-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="c4780-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c4780-134">已完成</span><span class="sxs-lookup"><span data-stu-id="c4780-134">Completed</span></span>|<span data-ttu-id="c4780-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="c4780-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="c4780-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="c4780-136">Deleted</span></span>|<span data-ttu-id="c4780-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="c4780-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="c4780-138">Idle</span><span class="sxs-lookup"><span data-stu-id="c4780-138">Idle</span></span>|<span data-ttu-id="c4780-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c4780-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c4780-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="c4780-140">Persisted</span></span>|<span data-ttu-id="c4780-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="c4780-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="c4780-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="c4780-142">Resumed</span></span>|<span data-ttu-id="c4780-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="c4780-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="c4780-144">Started</span><span class="sxs-lookup"><span data-stu-id="c4780-144">Started</span></span>|<span data-ttu-id="c4780-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="c4780-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="c4780-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="c4780-146">UnhandledException</span></span>|<span data-ttu-id="c4780-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="c4780-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="c4780-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="c4780-148">Unloaded</span></span>|<span data-ttu-id="c4780-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="c4780-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="c4780-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="c4780-150">Canceled</span></span>|<span data-ttu-id="c4780-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="c4780-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="c4780-152">挂起</span><span class="sxs-lookup"><span data-stu-id="c4780-152">Suspended</span></span>|<span data-ttu-id="c4780-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="c4780-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="c4780-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="c4780-154">Terminated</span></span>|<span data-ttu-id="c4780-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="c4780-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="c4780-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="c4780-156">Unsuspended</span></span>|<span data-ttu-id="c4780-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="c4780-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c4780-158">示例</span><span class="sxs-lookup"><span data-stu-id="c4780-158">Example</span></span>  
 <span data-ttu-id="c4780-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c4780-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4780-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4780-160">See Also</span></span>  
 <span data-ttu-id="c4780-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c4780-161"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="c4780-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c4780-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="c4780-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="c4780-163"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="c4780-164">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c4780-164">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="c4780-165">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c4780-165">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
