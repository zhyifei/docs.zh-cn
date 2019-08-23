---
title: <states>WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef4ce4b6fa6e60ead10b196b10a7c1489e15ac25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938981"
---
# <a name="states-of-wcf-workflowinstancequery"></a><span data-ttu-id="c17e6-102">\<WCF、 \<workflowInstanceQuery > 的状态 ></span><span class="sxs-lookup"><span data-stu-id="c17e6-102">\<states> of WCF, \<workflowInstanceQuery></span></span>

<span data-ttu-id="c17e6-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="c17e6-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="c17e6-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c17e6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c17e6-105">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="c17e6-105">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="c17e6-106">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="c17e6-106">\<profiles></span></span>  
<span data-ttu-id="c17e6-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c17e6-107">\<trackingProfile></span></span>  
<span data-ttu-id="c17e6-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="c17e6-108">\<workflow></span></span>  
<span data-ttu-id="c17e6-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="c17e6-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="c17e6-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c17e6-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="c17e6-111">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="c17e6-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c17e6-112">语法</span><span class="sxs-lookup"><span data-stu-id="c17e6-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c17e6-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c17e6-113">Attributes and elements</span></span>

<span data-ttu-id="c17e6-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c17e6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c17e6-115">特性</span><span class="sxs-lookup"><span data-stu-id="c17e6-115">Attributes</span></span>  

<span data-ttu-id="c17e6-116">无。</span><span class="sxs-lookup"><span data-stu-id="c17e6-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c17e6-117">子元素</span><span class="sxs-lookup"><span data-stu-id="c17e6-117">Child elements</span></span>
  
|<span data-ttu-id="c17e6-118">元素</span><span class="sxs-lookup"><span data-stu-id="c17e6-118">Element</span></span>|<span data-ttu-id="c17e6-119">描述</span><span class="sxs-lookup"><span data-stu-id="c17e6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c17e6-120">\<states></span><span class="sxs-lookup"><span data-stu-id="c17e6-120">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="c17e6-121">创建跟踪记录时已跟踪工作流实例中的一个已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="c17e6-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c17e6-122">父元素</span><span class="sxs-lookup"><span data-stu-id="c17e6-122">Parent elements</span></span>  
  
|<span data-ttu-id="c17e6-123">元素</span><span class="sxs-lookup"><span data-stu-id="c17e6-123">Element</span></span>|<span data-ttu-id="c17e6-124">描述</span><span class="sxs-lookup"><span data-stu-id="c17e6-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c17e6-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c17e6-125">\<workflowInstanceQuery></span></span>](../windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="c17e6-126">一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="c17e6-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c17e6-127">备注</span><span class="sxs-lookup"><span data-stu-id="c17e6-127">Remarks</span></span>

<span data-ttu-id="c17e6-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="c17e6-128">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="c17e6-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="c17e6-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="c17e6-130">状态</span><span class="sxs-lookup"><span data-stu-id="c17e6-130">State</span></span>|<span data-ttu-id="c17e6-131">描述</span><span class="sxs-lookup"><span data-stu-id="c17e6-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c17e6-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="c17e6-132">Aborted</span></span>|<span data-ttu-id="c17e6-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="c17e6-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c17e6-134">已完成</span><span class="sxs-lookup"><span data-stu-id="c17e6-134">Completed</span></span>|<span data-ttu-id="c17e6-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="c17e6-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="c17e6-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="c17e6-136">Deleted</span></span>|<span data-ttu-id="c17e6-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="c17e6-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="c17e6-138">Idle</span><span class="sxs-lookup"><span data-stu-id="c17e6-138">Idle</span></span>|<span data-ttu-id="c17e6-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c17e6-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c17e6-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="c17e6-140">Persisted</span></span>|<span data-ttu-id="c17e6-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="c17e6-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="c17e6-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="c17e6-142">Resumed</span></span>|<span data-ttu-id="c17e6-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="c17e6-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="c17e6-144">已开始</span><span class="sxs-lookup"><span data-stu-id="c17e6-144">Started</span></span>|<span data-ttu-id="c17e6-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="c17e6-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="c17e6-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="c17e6-146">UnhandledException</span></span>|<span data-ttu-id="c17e6-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="c17e6-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="c17e6-148">已卸载</span><span class="sxs-lookup"><span data-stu-id="c17e6-148">Unloaded</span></span>|<span data-ttu-id="c17e6-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="c17e6-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="c17e6-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="c17e6-150">Canceled</span></span>|<span data-ttu-id="c17e6-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="c17e6-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="c17e6-152">挂起的</span><span class="sxs-lookup"><span data-stu-id="c17e6-152">Suspended</span></span>|<span data-ttu-id="c17e6-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="c17e6-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="c17e6-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="c17e6-154">Terminated</span></span>|<span data-ttu-id="c17e6-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="c17e6-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="c17e6-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="c17e6-156">Unsuspended</span></span>|<span data-ttu-id="c17e6-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="c17e6-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c17e6-158">示例</span><span class="sxs-lookup"><span data-stu-id="c17e6-158">Example</span></span>

<span data-ttu-id="c17e6-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c17e6-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="c17e6-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="c17e6-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c17e6-161">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c17e6-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c17e6-162">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c17e6-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
