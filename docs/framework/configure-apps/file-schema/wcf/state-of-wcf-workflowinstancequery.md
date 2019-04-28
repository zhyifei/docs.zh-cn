---
title: <state> WCF <workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 1615c83ffe0735d9e55e822f2651da41d02b1610
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757958"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="bf973-102">\<状态 > 的 WCF， \<workflowInstanceQuery ></span><span class="sxs-lookup"><span data-stu-id="bf973-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="bf973-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="bf973-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="bf973-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="bf973-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="bf973-105">\<system.serviceModel></span></span>  
<span data-ttu-id="bf973-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="bf973-106">\<tracking></span></span>  
<span data-ttu-id="bf973-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="bf973-107">\<profiles></span></span>  
<span data-ttu-id="bf973-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="bf973-108">\<trackingProfile></span></span>  
<span data-ttu-id="bf973-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="bf973-109">\<workflow></span></span>  
<span data-ttu-id="bf973-110">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="bf973-110">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="bf973-111">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="bf973-111">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="bf973-112">\<states></span><span class="sxs-lookup"><span data-stu-id="bf973-112">\<states></span></span>  
<span data-ttu-id="bf973-113">\<state></span><span class="sxs-lookup"><span data-stu-id="bf973-113">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf973-114">语法</span><span class="sxs-lookup"><span data-stu-id="bf973-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf973-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bf973-115">Attributes and elements</span></span>

<span data-ttu-id="bf973-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bf973-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="bf973-117">特性</span><span class="sxs-lookup"><span data-stu-id="bf973-117">Attributes</span></span>

|<span data-ttu-id="bf973-118">特性</span><span class="sxs-lookup"><span data-stu-id="bf973-118">Attribute</span></span>|<span data-ttu-id="bf973-119">描述</span><span class="sxs-lookup"><span data-stu-id="bf973-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bf973-120">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf973-121">子元素</span><span class="sxs-lookup"><span data-stu-id="bf973-121">Child elements</span></span>

<span data-ttu-id="bf973-122">无。</span><span class="sxs-lookup"><span data-stu-id="bf973-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="bf973-123">父元素</span><span class="sxs-lookup"><span data-stu-id="bf973-123">Parent elements</span></span>

|<span data-ttu-id="bf973-124">元素</span><span class="sxs-lookup"><span data-stu-id="bf973-124">Element</span></span>|<span data-ttu-id="bf973-125">描述</span><span class="sxs-lookup"><span data-stu-id="bf973-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf973-126">\<states></span><span class="sxs-lookup"><span data-stu-id="bf973-126">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="bf973-127">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="bf973-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf973-128">备注</span><span class="sxs-lookup"><span data-stu-id="bf973-128">Remarks</span></span>  

<span data-ttu-id="bf973-129">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="bf973-129">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="bf973-130">可能的状态值如下表所述：</span><span class="sxs-lookup"><span data-stu-id="bf973-130">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="bf973-131">状态</span><span class="sxs-lookup"><span data-stu-id="bf973-131">State</span></span>|<span data-ttu-id="bf973-132">描述</span><span class="sxs-lookup"><span data-stu-id="bf973-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="bf973-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="bf973-133">Aborted</span></span>|<span data-ttu-id="bf973-134">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="bf973-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="bf973-135">已完成</span><span class="sxs-lookup"><span data-stu-id="bf973-135">Completed</span></span>|<span data-ttu-id="bf973-136">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="bf973-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="bf973-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="bf973-137">Deleted</span></span>|<span data-ttu-id="bf973-138">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="bf973-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="bf973-139">Idle</span><span class="sxs-lookup"><span data-stu-id="bf973-139">Idle</span></span>|<span data-ttu-id="bf973-140">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="bf973-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="bf973-141">Persisted</span></span>|<span data-ttu-id="bf973-142">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="bf973-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="bf973-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="bf973-143">Resumed</span></span>|<span data-ttu-id="bf973-144">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="bf973-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="bf973-145">已开始</span><span class="sxs-lookup"><span data-stu-id="bf973-145">Started</span></span>|<span data-ttu-id="bf973-146">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="bf973-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="bf973-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="bf973-147">UnhandledException</span></span>|<span data-ttu-id="bf973-148">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="bf973-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="bf973-149">已卸载</span><span class="sxs-lookup"><span data-stu-id="bf973-149">Unloaded</span></span>|<span data-ttu-id="bf973-150">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="bf973-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="bf973-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="bf973-151">Canceled</span></span>|<span data-ttu-id="bf973-152">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="bf973-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="bf973-153">挂起的</span><span class="sxs-lookup"><span data-stu-id="bf973-153">Suspended</span></span>|<span data-ttu-id="bf973-154">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="bf973-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="bf973-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="bf973-155">Terminated</span></span>|<span data-ttu-id="bf973-156">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="bf973-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="bf973-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="bf973-157">Unsuspended</span></span>|<span data-ttu-id="bf973-158">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="bf973-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf973-159">示例</span><span class="sxs-lookup"><span data-stu-id="bf973-159">Example</span></span>

<span data-ttu-id="bf973-160">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="bf973-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="bf973-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf973-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bf973-162">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="bf973-162">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bf973-163">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="bf973-163">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
