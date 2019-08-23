---
title: <state>WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 99387a8f60e96beb2ec7706d9abf4bb6ae84b868
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938210"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="76a18-102">\<WCF \<> 状态 ></span><span class="sxs-lookup"><span data-stu-id="76a18-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="76a18-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="76a18-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="76a18-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="76a18-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="76a18-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="76a18-105">\<system.serviceModel></span></span>  
<span data-ttu-id="76a18-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="76a18-106">\<tracking></span></span>  
<span data-ttu-id="76a18-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="76a18-107">\<profiles></span></span>  
<span data-ttu-id="76a18-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="76a18-108">\<trackingProfile></span></span>  
<span data-ttu-id="76a18-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="76a18-109">\<workflow></span></span>  
<span data-ttu-id="76a18-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="76a18-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="76a18-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="76a18-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="76a18-112">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="76a18-112">\<states></span></span>  
<span data-ttu-id="76a18-113">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="76a18-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a18-114">语法</span><span class="sxs-lookup"><span data-stu-id="76a18-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
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
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="76a18-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="76a18-115">Attributes and elements</span></span>

<span data-ttu-id="76a18-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="76a18-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="76a18-117">特性</span><span class="sxs-lookup"><span data-stu-id="76a18-117">Attributes</span></span>

|<span data-ttu-id="76a18-118">特性</span><span class="sxs-lookup"><span data-stu-id="76a18-118">Attribute</span></span>|<span data-ttu-id="76a18-119">描述</span><span class="sxs-lookup"><span data-stu-id="76a18-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="76a18-120">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="76a18-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="76a18-121">子元素</span><span class="sxs-lookup"><span data-stu-id="76a18-121">Child elements</span></span>

<span data-ttu-id="76a18-122">无。</span><span class="sxs-lookup"><span data-stu-id="76a18-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="76a18-123">父元素</span><span class="sxs-lookup"><span data-stu-id="76a18-123">Parent elements</span></span>

|<span data-ttu-id="76a18-124">元素</span><span class="sxs-lookup"><span data-stu-id="76a18-124">Element</span></span>|<span data-ttu-id="76a18-125">描述</span><span class="sxs-lookup"><span data-stu-id="76a18-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="76a18-126">\<states></span><span class="sxs-lookup"><span data-stu-id="76a18-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="76a18-127">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="76a18-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76a18-128">备注</span><span class="sxs-lookup"><span data-stu-id="76a18-128">Remarks</span></span>  

<span data-ttu-id="76a18-129">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="76a18-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="76a18-130">下表描述了可能的状态值:</span><span class="sxs-lookup"><span data-stu-id="76a18-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="76a18-131">状态</span><span class="sxs-lookup"><span data-stu-id="76a18-131">State</span></span>|<span data-ttu-id="76a18-132">描述</span><span class="sxs-lookup"><span data-stu-id="76a18-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="76a18-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="76a18-133">Aborted</span></span>|<span data-ttu-id="76a18-134">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="76a18-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="76a18-135">已完成</span><span class="sxs-lookup"><span data-stu-id="76a18-135">Completed</span></span>|<span data-ttu-id="76a18-136">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="76a18-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="76a18-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="76a18-137">Deleted</span></span>|<span data-ttu-id="76a18-138">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="76a18-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="76a18-139">Idle</span><span class="sxs-lookup"><span data-stu-id="76a18-139">Idle</span></span>|<span data-ttu-id="76a18-140">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="76a18-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="76a18-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="76a18-141">Persisted</span></span>|<span data-ttu-id="76a18-142">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="76a18-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="76a18-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="76a18-143">Resumed</span></span>|<span data-ttu-id="76a18-144">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="76a18-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="76a18-145">已开始</span><span class="sxs-lookup"><span data-stu-id="76a18-145">Started</span></span>|<span data-ttu-id="76a18-146">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="76a18-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="76a18-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="76a18-147">UnhandledException</span></span>|<span data-ttu-id="76a18-148">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="76a18-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="76a18-149">已卸载</span><span class="sxs-lookup"><span data-stu-id="76a18-149">Unloaded</span></span>|<span data-ttu-id="76a18-150">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="76a18-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="76a18-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="76a18-151">Canceled</span></span>|<span data-ttu-id="76a18-152">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="76a18-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="76a18-153">挂起的</span><span class="sxs-lookup"><span data-stu-id="76a18-153">Suspended</span></span>|<span data-ttu-id="76a18-154">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="76a18-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="76a18-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="76a18-155">Terminated</span></span>|<span data-ttu-id="76a18-156">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="76a18-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="76a18-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="76a18-157">Unsuspended</span></span>|<span data-ttu-id="76a18-158">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="76a18-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="76a18-159">示例</span><span class="sxs-lookup"><span data-stu-id="76a18-159">Example</span></span>

<span data-ttu-id="76a18-160">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="76a18-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="76a18-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="76a18-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="76a18-162">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="76a18-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="76a18-163">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="76a18-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
