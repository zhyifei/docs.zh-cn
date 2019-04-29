---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 30cb2efa4c00c8b292a8ace6a03306d6ac76a7f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797795"
---
# <a name="states"></a><span data-ttu-id="ad835-101">\<states></span><span class="sxs-lookup"><span data-stu-id="ad835-101">\<states></span></span>
<span data-ttu-id="ad835-102">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="ad835-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="ad835-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ad835-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ad835-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ad835-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ad835-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ad835-105">\<tracking></span></span>  
<span data-ttu-id="ad835-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ad835-106">\<trackingProfile></span></span>  
<span data-ttu-id="ad835-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ad835-107">\<workflow></span></span>  
<span data-ttu-id="ad835-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="ad835-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="ad835-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="ad835-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="ad835-110">\<states></span><span class="sxs-lookup"><span data-stu-id="ad835-110">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad835-111">语法</span><span class="sxs-lookup"><span data-stu-id="ad835-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad835-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ad835-112">Attributes and Elements</span></span>  
 <span data-ttu-id="ad835-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ad835-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad835-114">特性</span><span class="sxs-lookup"><span data-stu-id="ad835-114">Attributes</span></span>  
 <span data-ttu-id="ad835-115">无。</span><span class="sxs-lookup"><span data-stu-id="ad835-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ad835-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ad835-116">Child Elements</span></span>  
  
|<span data-ttu-id="ad835-117">元素</span><span class="sxs-lookup"><span data-stu-id="ad835-117">Element</span></span>|<span data-ttu-id="ad835-118">描述</span><span class="sxs-lookup"><span data-stu-id="ad835-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad835-119">\<state></span><span class="sxs-lookup"><span data-stu-id="ad835-119">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="ad835-120">创建跟踪记录时已跟踪工作流实例中的一个已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="ad835-120">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad835-121">父元素</span><span class="sxs-lookup"><span data-stu-id="ad835-121">Parent Elements</span></span>  
  
|<span data-ttu-id="ad835-122">元素</span><span class="sxs-lookup"><span data-stu-id="ad835-122">Element</span></span>|<span data-ttu-id="ad835-123">描述</span><span class="sxs-lookup"><span data-stu-id="ad835-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad835-124">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="ad835-124">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="ad835-125">一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="ad835-125">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad835-126">备注</span><span class="sxs-lookup"><span data-stu-id="ad835-126">Remarks</span></span>  
 <span data-ttu-id="ad835-127">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="ad835-127">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="ad835-128">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="ad835-128">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="ad835-129">状态</span><span class="sxs-lookup"><span data-stu-id="ad835-129">State</span></span>|<span data-ttu-id="ad835-130">描述</span><span class="sxs-lookup"><span data-stu-id="ad835-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ad835-131">Aborted</span><span class="sxs-lookup"><span data-stu-id="ad835-131">Aborted</span></span>|<span data-ttu-id="ad835-132">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="ad835-132">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="ad835-133">已完成</span><span class="sxs-lookup"><span data-stu-id="ad835-133">Completed</span></span>|<span data-ttu-id="ad835-134">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="ad835-134">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="ad835-135">Deleted</span><span class="sxs-lookup"><span data-stu-id="ad835-135">Deleted</span></span>|<span data-ttu-id="ad835-136">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="ad835-136">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="ad835-137">Idle</span><span class="sxs-lookup"><span data-stu-id="ad835-137">Idle</span></span>|<span data-ttu-id="ad835-138">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="ad835-138">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="ad835-139">Persisted</span><span class="sxs-lookup"><span data-stu-id="ad835-139">Persisted</span></span>|<span data-ttu-id="ad835-140">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="ad835-140">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="ad835-141">Resumed</span><span class="sxs-lookup"><span data-stu-id="ad835-141">Resumed</span></span>|<span data-ttu-id="ad835-142">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="ad835-142">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="ad835-143">已开始</span><span class="sxs-lookup"><span data-stu-id="ad835-143">Started</span></span>|<span data-ttu-id="ad835-144">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="ad835-144">The workflow instance is started.</span></span>|  
|<span data-ttu-id="ad835-145">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="ad835-145">UnhandledException</span></span>|<span data-ttu-id="ad835-146">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="ad835-146">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="ad835-147">已卸载</span><span class="sxs-lookup"><span data-stu-id="ad835-147">Unloaded</span></span>|<span data-ttu-id="ad835-148">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="ad835-148">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="ad835-149">Canceled</span><span class="sxs-lookup"><span data-stu-id="ad835-149">Canceled</span></span>|<span data-ttu-id="ad835-150">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="ad835-150">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="ad835-151">挂起的</span><span class="sxs-lookup"><span data-stu-id="ad835-151">Suspended</span></span>|<span data-ttu-id="ad835-152">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="ad835-152">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="ad835-153">Terminated</span><span class="sxs-lookup"><span data-stu-id="ad835-153">Terminated</span></span>|<span data-ttu-id="ad835-154">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="ad835-154">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="ad835-155">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="ad835-155">Unsuspended</span></span>|<span data-ttu-id="ad835-156">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="ad835-156">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ad835-157">示例</span><span class="sxs-lookup"><span data-stu-id="ad835-157">Example</span></span>  
 <span data-ttu-id="ad835-158">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="ad835-158">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad835-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad835-159">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ad835-160">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ad835-160">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ad835-161">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ad835-161">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
