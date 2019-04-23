---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 6f1a9474f3f12005df364a6fb84dc63aa1b68e04
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108156"
---
# <a name="state"></a><span data-ttu-id="c337b-101">\<state></span><span class="sxs-lookup"><span data-stu-id="c337b-101">\<state></span></span>
<span data-ttu-id="c337b-102">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="c337b-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="c337b-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c337b-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c337b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c337b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c337b-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c337b-105">\<tracking></span></span>  
<span data-ttu-id="c337b-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c337b-106">\<trackingProfile></span></span>  
<span data-ttu-id="c337b-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c337b-107">\<workflow></span></span>  
<span data-ttu-id="c337b-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="c337b-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="c337b-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="c337b-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="c337b-110">\<states></span><span class="sxs-lookup"><span data-stu-id="c337b-110">\<states></span></span>  
<span data-ttu-id="c337b-111">\<state></span><span class="sxs-lookup"><span data-stu-id="c337b-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c337b-112">语法</span><span class="sxs-lookup"><span data-stu-id="c337b-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c337b-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c337b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="c337b-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c337b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c337b-115">特性</span><span class="sxs-lookup"><span data-stu-id="c337b-115">Attributes</span></span>  
  
|<span data-ttu-id="c337b-116">特性</span><span class="sxs-lookup"><span data-stu-id="c337b-116">Attribute</span></span>|<span data-ttu-id="c337b-117">描述</span><span class="sxs-lookup"><span data-stu-id="c337b-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c337b-118">name</span><span class="sxs-lookup"><span data-stu-id="c337b-118">name</span></span>|<span data-ttu-id="c337b-119">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="c337b-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c337b-120">子元素</span><span class="sxs-lookup"><span data-stu-id="c337b-120">Child Elements</span></span>  
 <span data-ttu-id="c337b-121">无。</span><span class="sxs-lookup"><span data-stu-id="c337b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c337b-122">父元素</span><span class="sxs-lookup"><span data-stu-id="c337b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c337b-123">元素</span><span class="sxs-lookup"><span data-stu-id="c337b-123">Element</span></span>|<span data-ttu-id="c337b-124">描述</span><span class="sxs-lookup"><span data-stu-id="c337b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c337b-125">\<states></span><span class="sxs-lookup"><span data-stu-id="c337b-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="c337b-126">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="c337b-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c337b-127">备注</span><span class="sxs-lookup"><span data-stu-id="c337b-127">Remarks</span></span>  
 <span data-ttu-id="c337b-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="c337b-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="c337b-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="c337b-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="c337b-130">状态</span><span class="sxs-lookup"><span data-stu-id="c337b-130">State</span></span>|<span data-ttu-id="c337b-131">描述</span><span class="sxs-lookup"><span data-stu-id="c337b-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c337b-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="c337b-132">Aborted</span></span>|<span data-ttu-id="c337b-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="c337b-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="c337b-134">已完成</span><span class="sxs-lookup"><span data-stu-id="c337b-134">Completed</span></span>|<span data-ttu-id="c337b-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="c337b-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="c337b-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="c337b-136">Deleted</span></span>|<span data-ttu-id="c337b-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="c337b-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="c337b-138">Idle</span><span class="sxs-lookup"><span data-stu-id="c337b-138">Idle</span></span>|<span data-ttu-id="c337b-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c337b-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="c337b-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="c337b-140">Persisted</span></span>|<span data-ttu-id="c337b-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="c337b-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="c337b-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="c337b-142">Resumed</span></span>|<span data-ttu-id="c337b-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="c337b-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="c337b-144">已开始</span><span class="sxs-lookup"><span data-stu-id="c337b-144">Started</span></span>|<span data-ttu-id="c337b-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="c337b-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="c337b-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="c337b-146">UnhandledException</span></span>|<span data-ttu-id="c337b-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="c337b-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="c337b-148">已卸载</span><span class="sxs-lookup"><span data-stu-id="c337b-148">Unloaded</span></span>|<span data-ttu-id="c337b-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="c337b-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="c337b-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="c337b-150">Canceled</span></span>|<span data-ttu-id="c337b-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="c337b-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="c337b-152">挂起的</span><span class="sxs-lookup"><span data-stu-id="c337b-152">Suspended</span></span>|<span data-ttu-id="c337b-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="c337b-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="c337b-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="c337b-154">Terminated</span></span>|<span data-ttu-id="c337b-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="c337b-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="c337b-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="c337b-156">Unsuspended</span></span>|<span data-ttu-id="c337b-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="c337b-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c337b-158">示例</span><span class="sxs-lookup"><span data-stu-id="c337b-158">Example</span></span>  
 <span data-ttu-id="c337b-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c337b-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c337b-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="c337b-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c337b-161">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c337b-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c337b-162">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c337b-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
