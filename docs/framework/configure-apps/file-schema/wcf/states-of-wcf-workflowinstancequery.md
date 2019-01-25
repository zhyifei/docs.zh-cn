---
title: WCF 的 &lt;states&gt;，&lt;workflowInstanceQuery&gt;
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: 56e3c6ce5c86e468c9a4dd63021264703ab75b02
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540814"
---
# <a name="ltstatesgt-of-wcf-ltworkflowinstancequerygt"></a><span data-ttu-id="8ef32-102">WCF 的 &lt;states&gt;，&lt;workflowInstanceQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="8ef32-102">&lt;states&gt; of WCF, &lt;workflowInstanceQuery&gt;</span></span>

<span data-ttu-id="8ef32-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="8ef32-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
<span data-ttu-id="8ef32-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8ef32-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8ef32-105">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="8ef32-105">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="8ef32-106">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="8ef32-106">\<profiles></span></span>  
<span data-ttu-id="8ef32-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8ef32-107">\<trackingProfile></span></span>  
<span data-ttu-id="8ef32-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8ef32-108">\<workflow></span></span>  
<span data-ttu-id="8ef32-109">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="8ef32-109">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="8ef32-110">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="8ef32-110">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="8ef32-111">\<states></span><span class="sxs-lookup"><span data-stu-id="8ef32-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ef32-112">语法</span><span class="sxs-lookup"><span data-stu-id="8ef32-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ef32-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8ef32-113">Attributes and elements</span></span>

<span data-ttu-id="8ef32-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8ef32-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ef32-115">特性</span><span class="sxs-lookup"><span data-stu-id="8ef32-115">Attributes</span></span>  

<span data-ttu-id="8ef32-116">无。</span><span class="sxs-lookup"><span data-stu-id="8ef32-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8ef32-117">子元素</span><span class="sxs-lookup"><span data-stu-id="8ef32-117">Child elements</span></span>
  
|<span data-ttu-id="8ef32-118">元素</span><span class="sxs-lookup"><span data-stu-id="8ef32-118">Element</span></span>|<span data-ttu-id="8ef32-119">描述</span><span class="sxs-lookup"><span data-stu-id="8ef32-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ef32-120">\<states></span><span class="sxs-lookup"><span data-stu-id="8ef32-120">\<states></span></span>](state-of-wcf-workflowinstancequery.md)|<span data-ttu-id="8ef32-121">创建跟踪记录时已跟踪工作流实例中的一个已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="8ef32-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8ef32-122">父元素</span><span class="sxs-lookup"><span data-stu-id="8ef32-122">Parent elements</span></span>  
  
|<span data-ttu-id="8ef32-123">元素</span><span class="sxs-lookup"><span data-stu-id="8ef32-123">Element</span></span>|<span data-ttu-id="8ef32-124">描述</span><span class="sxs-lookup"><span data-stu-id="8ef32-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ef32-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="8ef32-125">\<workflowInstanceQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|<span data-ttu-id="8ef32-126">一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="8ef32-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ef32-127">备注</span><span class="sxs-lookup"><span data-stu-id="8ef32-127">Remarks</span></span>

<span data-ttu-id="8ef32-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="8ef32-128">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="8ef32-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="8ef32-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="8ef32-130">状态</span><span class="sxs-lookup"><span data-stu-id="8ef32-130">State</span></span>|<span data-ttu-id="8ef32-131">描述</span><span class="sxs-lookup"><span data-stu-id="8ef32-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8ef32-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="8ef32-132">Aborted</span></span>|<span data-ttu-id="8ef32-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="8ef32-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="8ef32-134">已完成</span><span class="sxs-lookup"><span data-stu-id="8ef32-134">Completed</span></span>|<span data-ttu-id="8ef32-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="8ef32-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="8ef32-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="8ef32-136">Deleted</span></span>|<span data-ttu-id="8ef32-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="8ef32-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="8ef32-138">Idle</span><span class="sxs-lookup"><span data-stu-id="8ef32-138">Idle</span></span>|<span data-ttu-id="8ef32-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="8ef32-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="8ef32-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="8ef32-140">Persisted</span></span>|<span data-ttu-id="8ef32-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="8ef32-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="8ef32-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="8ef32-142">Resumed</span></span>|<span data-ttu-id="8ef32-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="8ef32-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="8ef32-144">Started</span><span class="sxs-lookup"><span data-stu-id="8ef32-144">Started</span></span>|<span data-ttu-id="8ef32-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="8ef32-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="8ef32-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="8ef32-146">UnhandledException</span></span>|<span data-ttu-id="8ef32-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="8ef32-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="8ef32-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="8ef32-148">Unloaded</span></span>|<span data-ttu-id="8ef32-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="8ef32-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="8ef32-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="8ef32-150">Canceled</span></span>|<span data-ttu-id="8ef32-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="8ef32-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="8ef32-152">挂起</span><span class="sxs-lookup"><span data-stu-id="8ef32-152">Suspended</span></span>|<span data-ttu-id="8ef32-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="8ef32-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="8ef32-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="8ef32-154">Terminated</span></span>|<span data-ttu-id="8ef32-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="8ef32-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="8ef32-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="8ef32-156">Unsuspended</span></span>|<span data-ttu-id="8ef32-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="8ef32-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8ef32-158">示例</span><span class="sxs-lookup"><span data-stu-id="8ef32-158">Example</span></span>

<span data-ttu-id="8ef32-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="8ef32-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="8ef32-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ef32-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8ef32-161">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8ef32-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8ef32-162">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8ef32-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
