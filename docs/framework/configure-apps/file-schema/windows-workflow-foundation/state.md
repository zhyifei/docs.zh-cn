---
title: '&lt;state&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ca170740fbe55547c9897054f9c4782c2d25afdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt"></a><span data-ttu-id="735aa-102">&lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="735aa-102">&lt;state&gt;</span></span>
<span data-ttu-id="735aa-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="735aa-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="735aa-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="735aa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="735aa-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="735aa-105">\<system.serviceModel></span></span>  
<span data-ttu-id="735aa-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="735aa-106">\<tracking></span></span>  
<span data-ttu-id="735aa-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="735aa-107">\<trackingProfile></span></span>  
<span data-ttu-id="735aa-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="735aa-108">\<workflow></span></span>  
<span data-ttu-id="735aa-109">\<workflowInstanceQueries ></span><span class="sxs-lookup"><span data-stu-id="735aa-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="735aa-110">\<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="735aa-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="735aa-111">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="735aa-111">\<states></span></span>  
<span data-ttu-id="735aa-112">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="735aa-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="735aa-113">语法</span><span class="sxs-lookup"><span data-stu-id="735aa-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name" />
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="735aa-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="735aa-114">Attributes and Elements</span></span>  
 <span data-ttu-id="735aa-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="735aa-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="735aa-116">特性</span><span class="sxs-lookup"><span data-stu-id="735aa-116">Attributes</span></span>  
  
|<span data-ttu-id="735aa-117">特性</span><span class="sxs-lookup"><span data-stu-id="735aa-117">Attribute</span></span>|<span data-ttu-id="735aa-118">描述</span><span class="sxs-lookup"><span data-stu-id="735aa-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="735aa-119">name</span><span class="sxs-lookup"><span data-stu-id="735aa-119">name</span></span>|<span data-ttu-id="735aa-120">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="735aa-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="735aa-121">子元素</span><span class="sxs-lookup"><span data-stu-id="735aa-121">Child Elements</span></span>  
 <span data-ttu-id="735aa-122">无。</span><span class="sxs-lookup"><span data-stu-id="735aa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="735aa-123">父元素</span><span class="sxs-lookup"><span data-stu-id="735aa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="735aa-124">元素</span><span class="sxs-lookup"><span data-stu-id="735aa-124">Element</span></span>|<span data-ttu-id="735aa-125">描述</span><span class="sxs-lookup"><span data-stu-id="735aa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="735aa-126">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="735aa-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="735aa-127">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="735aa-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="735aa-128">备注</span><span class="sxs-lookup"><span data-stu-id="735aa-128">Remarks</span></span>  
 <span data-ttu-id="735aa-129">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="735aa-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="735aa-130">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="735aa-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="735aa-131">状态</span><span class="sxs-lookup"><span data-stu-id="735aa-131">State</span></span>|<span data-ttu-id="735aa-132">描述</span><span class="sxs-lookup"><span data-stu-id="735aa-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="735aa-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="735aa-133">Aborted</span></span>|<span data-ttu-id="735aa-134">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="735aa-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="735aa-135">已完成</span><span class="sxs-lookup"><span data-stu-id="735aa-135">Completed</span></span>|<span data-ttu-id="735aa-136">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="735aa-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="735aa-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="735aa-137">Deleted</span></span>|<span data-ttu-id="735aa-138">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="735aa-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="735aa-139">Idle</span><span class="sxs-lookup"><span data-stu-id="735aa-139">Idle</span></span>|<span data-ttu-id="735aa-140">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="735aa-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="735aa-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="735aa-141">Persisted</span></span>|<span data-ttu-id="735aa-142">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="735aa-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="735aa-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="735aa-143">Resumed</span></span>|<span data-ttu-id="735aa-144">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="735aa-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="735aa-145">Started</span><span class="sxs-lookup"><span data-stu-id="735aa-145">Started</span></span>|<span data-ttu-id="735aa-146">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="735aa-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="735aa-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="735aa-147">UnhandledException</span></span>|<span data-ttu-id="735aa-148">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="735aa-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="735aa-149">Unloaded</span><span class="sxs-lookup"><span data-stu-id="735aa-149">Unloaded</span></span>|<span data-ttu-id="735aa-150">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="735aa-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="735aa-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="735aa-151">Canceled</span></span>|<span data-ttu-id="735aa-152">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="735aa-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="735aa-153">挂起</span><span class="sxs-lookup"><span data-stu-id="735aa-153">Suspended</span></span>|<span data-ttu-id="735aa-154">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="735aa-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="735aa-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="735aa-155">Terminated</span></span>|<span data-ttu-id="735aa-156">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="735aa-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="735aa-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="735aa-157">Unsuspended</span></span>|<span data-ttu-id="735aa-158">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="735aa-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="735aa-159">示例</span><span class="sxs-lookup"><span data-stu-id="735aa-159">Example</span></span>  
 <span data-ttu-id="735aa-160">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="735aa-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="735aa-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="735aa-161">See Also</span></span>  
 <span data-ttu-id="735aa-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="735aa-162"><xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="735aa-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="735aa-163"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="735aa-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="735aa-164"><xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType></span></span>      
 [<span data-ttu-id="735aa-165">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="735aa-165">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="735aa-166">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="735aa-166">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
