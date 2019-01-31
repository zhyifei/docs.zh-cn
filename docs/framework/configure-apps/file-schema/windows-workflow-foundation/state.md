---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 38b0522b93c051473d7cdc28ae955cc3b7b58efe
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287230"
---
# <a name="state"></a><span data-ttu-id="43547-101">\<state></span><span class="sxs-lookup"><span data-stu-id="43547-101">\<state></span></span>
<span data-ttu-id="43547-102">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="43547-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="43547-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="43547-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="43547-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="43547-104">\<system.serviceModel></span></span>  
<span data-ttu-id="43547-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="43547-105">\<tracking></span></span>  
<span data-ttu-id="43547-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="43547-106">\<trackingProfile></span></span>  
<span data-ttu-id="43547-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="43547-107">\<workflow></span></span>  
<span data-ttu-id="43547-108">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="43547-108">\<workflowInstanceQueries></span></span>  
<span data-ttu-id="43547-109">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="43547-109">\<workflowInstanceQuery></span></span>  
<span data-ttu-id="43547-110">\<states></span><span class="sxs-lookup"><span data-stu-id="43547-110">\<states></span></span>  
<span data-ttu-id="43547-111">\<state></span><span class="sxs-lookup"><span data-stu-id="43547-111">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43547-112">语法</span><span class="sxs-lookup"><span data-stu-id="43547-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43547-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="43547-113">Attributes and Elements</span></span>  
 <span data-ttu-id="43547-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="43547-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43547-115">特性</span><span class="sxs-lookup"><span data-stu-id="43547-115">Attributes</span></span>  
  
|<span data-ttu-id="43547-116">特性</span><span class="sxs-lookup"><span data-stu-id="43547-116">Attribute</span></span>|<span data-ttu-id="43547-117">描述</span><span class="sxs-lookup"><span data-stu-id="43547-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43547-118">name</span><span class="sxs-lookup"><span data-stu-id="43547-118">name</span></span>|<span data-ttu-id="43547-119">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="43547-119">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43547-120">子元素</span><span class="sxs-lookup"><span data-stu-id="43547-120">Child Elements</span></span>  
 <span data-ttu-id="43547-121">无。</span><span class="sxs-lookup"><span data-stu-id="43547-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43547-122">父元素</span><span class="sxs-lookup"><span data-stu-id="43547-122">Parent Elements</span></span>  
  
|<span data-ttu-id="43547-123">元素</span><span class="sxs-lookup"><span data-stu-id="43547-123">Element</span></span>|<span data-ttu-id="43547-124">描述</span><span class="sxs-lookup"><span data-stu-id="43547-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43547-125">\<states></span><span class="sxs-lookup"><span data-stu-id="43547-125">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="43547-126">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="43547-126">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43547-127">备注</span><span class="sxs-lookup"><span data-stu-id="43547-127">Remarks</span></span>  
 <span data-ttu-id="43547-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="43547-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="43547-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="43547-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="43547-130">状态</span><span class="sxs-lookup"><span data-stu-id="43547-130">State</span></span>|<span data-ttu-id="43547-131">描述</span><span class="sxs-lookup"><span data-stu-id="43547-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="43547-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="43547-132">Aborted</span></span>|<span data-ttu-id="43547-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="43547-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="43547-134">已完成</span><span class="sxs-lookup"><span data-stu-id="43547-134">Completed</span></span>|<span data-ttu-id="43547-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="43547-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="43547-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="43547-136">Deleted</span></span>|<span data-ttu-id="43547-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="43547-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="43547-138">Idle</span><span class="sxs-lookup"><span data-stu-id="43547-138">Idle</span></span>|<span data-ttu-id="43547-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="43547-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="43547-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="43547-140">Persisted</span></span>|<span data-ttu-id="43547-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="43547-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="43547-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="43547-142">Resumed</span></span>|<span data-ttu-id="43547-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="43547-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="43547-144">Started</span><span class="sxs-lookup"><span data-stu-id="43547-144">Started</span></span>|<span data-ttu-id="43547-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="43547-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="43547-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="43547-146">UnhandledException</span></span>|<span data-ttu-id="43547-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="43547-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="43547-148">Unloaded</span><span class="sxs-lookup"><span data-stu-id="43547-148">Unloaded</span></span>|<span data-ttu-id="43547-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="43547-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="43547-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="43547-150">Canceled</span></span>|<span data-ttu-id="43547-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="43547-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="43547-152">挂起</span><span class="sxs-lookup"><span data-stu-id="43547-152">Suspended</span></span>|<span data-ttu-id="43547-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="43547-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="43547-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="43547-154">Terminated</span></span>|<span data-ttu-id="43547-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="43547-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="43547-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="43547-156">Unsuspended</span></span>|<span data-ttu-id="43547-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="43547-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="43547-158">示例</span><span class="sxs-lookup"><span data-stu-id="43547-158">Example</span></span>  
 <span data-ttu-id="43547-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="43547-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43547-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="43547-160">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="43547-161">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="43547-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="43547-162">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="43547-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
