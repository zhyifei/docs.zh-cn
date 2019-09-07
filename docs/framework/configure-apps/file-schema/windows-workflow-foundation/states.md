---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 1a7c839a5ff8fac9470aea71a4886d9000086e9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398616"
---
# <a name="states"></a><span data-ttu-id="b8e9f-101">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="b8e9f-101">\<states></span></span>
<span data-ttu-id="b8e9f-102">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="b8e9f-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b8e9f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b8e9f-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b8e9f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b8e9f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b8e9f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b8e9f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflowinstancequeries&gt; >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="b8e9f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="b8e9f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="b8e9f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状态 >**</span><span class="sxs-lookup"><span data-stu-id="b8e9f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<states>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8e9f-112">语法</span><span class="sxs-lookup"><span data-stu-id="b8e9f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b8e9f-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b8e9f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b8e9f-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b8e9f-115">特性</span><span class="sxs-lookup"><span data-stu-id="b8e9f-115">Attributes</span></span>  
 <span data-ttu-id="b8e9f-116">无。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b8e9f-117">子元素</span><span class="sxs-lookup"><span data-stu-id="b8e9f-117">Child Elements</span></span>  
  
|<span data-ttu-id="b8e9f-118">元素</span><span class="sxs-lookup"><span data-stu-id="b8e9f-118">Element</span></span>|<span data-ttu-id="b8e9f-119">描述</span><span class="sxs-lookup"><span data-stu-id="b8e9f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8e9f-120">\<state></span><span class="sxs-lookup"><span data-stu-id="b8e9f-120">\<state></span></span>](states.md)|<span data-ttu-id="b8e9f-121">创建跟踪记录时已跟踪工作流实例中的一个已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-121">A subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b8e9f-122">父元素</span><span class="sxs-lookup"><span data-stu-id="b8e9f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b8e9f-123">元素</span><span class="sxs-lookup"><span data-stu-id="b8e9f-123">Element</span></span>|<span data-ttu-id="b8e9f-124">描述</span><span class="sxs-lookup"><span data-stu-id="b8e9f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b8e9f-125">\<workflowInstanceQuery></span><span class="sxs-lookup"><span data-stu-id="b8e9f-125">\<workflowInstanceQuery></span></span>](workflowinstancequery.md)|<span data-ttu-id="b8e9f-126">一个查询，该查询跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-126">A query that tracks workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8e9f-127">备注</span><span class="sxs-lookup"><span data-stu-id="b8e9f-127">Remarks</span></span>  
 <span data-ttu-id="b8e9f-128">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-128">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="b8e9f-129">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-129">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="b8e9f-130">状态</span><span class="sxs-lookup"><span data-stu-id="b8e9f-130">State</span></span>|<span data-ttu-id="b8e9f-131">描述</span><span class="sxs-lookup"><span data-stu-id="b8e9f-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b8e9f-132">Aborted</span><span class="sxs-lookup"><span data-stu-id="b8e9f-132">Aborted</span></span>|<span data-ttu-id="b8e9f-133">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-133">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="b8e9f-134">已完成</span><span class="sxs-lookup"><span data-stu-id="b8e9f-134">Completed</span></span>|<span data-ttu-id="b8e9f-135">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-135">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="b8e9f-136">Deleted</span><span class="sxs-lookup"><span data-stu-id="b8e9f-136">Deleted</span></span>|<span data-ttu-id="b8e9f-137">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-137">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="b8e9f-138">Idle</span><span class="sxs-lookup"><span data-stu-id="b8e9f-138">Idle</span></span>|<span data-ttu-id="b8e9f-139">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-139">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="b8e9f-140">Persisted</span><span class="sxs-lookup"><span data-stu-id="b8e9f-140">Persisted</span></span>|<span data-ttu-id="b8e9f-141">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-141">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="b8e9f-142">Resumed</span><span class="sxs-lookup"><span data-stu-id="b8e9f-142">Resumed</span></span>|<span data-ttu-id="b8e9f-143">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-143">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="b8e9f-144">已开始</span><span class="sxs-lookup"><span data-stu-id="b8e9f-144">Started</span></span>|<span data-ttu-id="b8e9f-145">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-145">The workflow instance is started.</span></span>|  
|<span data-ttu-id="b8e9f-146">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="b8e9f-146">UnhandledException</span></span>|<span data-ttu-id="b8e9f-147">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-147">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="b8e9f-148">已卸载</span><span class="sxs-lookup"><span data-stu-id="b8e9f-148">Unloaded</span></span>|<span data-ttu-id="b8e9f-149">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-149">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="b8e9f-150">Canceled</span><span class="sxs-lookup"><span data-stu-id="b8e9f-150">Canceled</span></span>|<span data-ttu-id="b8e9f-151">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-151">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="b8e9f-152">挂起的</span><span class="sxs-lookup"><span data-stu-id="b8e9f-152">Suspended</span></span>|<span data-ttu-id="b8e9f-153">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-153">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="b8e9f-154">Terminated</span><span class="sxs-lookup"><span data-stu-id="b8e9f-154">Terminated</span></span>|<span data-ttu-id="b8e9f-155">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-155">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="b8e9f-156">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="b8e9f-156">Unsuspended</span></span>|<span data-ttu-id="b8e9f-157">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-157">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b8e9f-158">示例</span><span class="sxs-lookup"><span data-stu-id="b8e9f-158">Example</span></span>  
 <span data-ttu-id="b8e9f-159">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="b8e9f-159">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8e9f-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e9f-160">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b8e9f-161">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b8e9f-161">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b8e9f-162">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b8e9f-162">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
