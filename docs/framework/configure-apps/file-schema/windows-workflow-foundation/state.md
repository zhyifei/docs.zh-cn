---
title: <state>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 619414f2-61c2-4427-9977-d05009e343db
ms.openlocfilehash: 7af75182cf38a6acb8a31b71e8b7b42103f8046b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398639"
---
# <a name="state"></a><span data-ttu-id="1079a-101">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="1079a-101">\<state></span></span>
<span data-ttu-id="1079a-102">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="1079a-102">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="1079a-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1079a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1079a-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1079a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1079a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1079a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1079a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflowinstancequeries&gt; >** ](workflowinstancequeries.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries.md)</span></span>\
<span data-ttu-id="1079a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery.md)</span></span>\
<span data-ttu-id="1079a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<状态 >** ](states.md)</span><span class="sxs-lookup"><span data-stu-id="1079a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states.md)</span></span>\
<span data-ttu-id="1079a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状态 >**</span><span class="sxs-lookup"><span data-stu-id="1079a-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1079a-113">语法</span><span class="sxs-lookup"><span data-stu-id="1079a-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1079a-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1079a-114">Attributes and Elements</span></span>  
 <span data-ttu-id="1079a-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1079a-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1079a-116">特性</span><span class="sxs-lookup"><span data-stu-id="1079a-116">Attributes</span></span>  
  
|<span data-ttu-id="1079a-117">特性</span><span class="sxs-lookup"><span data-stu-id="1079a-117">Attribute</span></span>|<span data-ttu-id="1079a-118">描述</span><span class="sxs-lookup"><span data-stu-id="1079a-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1079a-119">NAME</span><span class="sxs-lookup"><span data-stu-id="1079a-119">name</span></span>|<span data-ttu-id="1079a-120">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="1079a-120">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1079a-121">子元素</span><span class="sxs-lookup"><span data-stu-id="1079a-121">Child Elements</span></span>  
 <span data-ttu-id="1079a-122">无。</span><span class="sxs-lookup"><span data-stu-id="1079a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1079a-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1079a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1079a-124">元素</span><span class="sxs-lookup"><span data-stu-id="1079a-124">Element</span></span>|<span data-ttu-id="1079a-125">描述</span><span class="sxs-lookup"><span data-stu-id="1079a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1079a-126">\<states></span><span class="sxs-lookup"><span data-stu-id="1079a-126">\<states></span></span>](states.md)|<span data-ttu-id="1079a-127">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="1079a-127">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1079a-128">备注</span><span class="sxs-lookup"><span data-stu-id="1079a-128">Remarks</span></span>  
 <span data-ttu-id="1079a-129">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="1079a-129">The returned records are filtered by the states in this collection.</span></span>  
  
 <span data-ttu-id="1079a-130">下表中列出了可能的状态值。</span><span class="sxs-lookup"><span data-stu-id="1079a-130">Possible state values are described in the following table.</span></span>  
  
|<span data-ttu-id="1079a-131">状态</span><span class="sxs-lookup"><span data-stu-id="1079a-131">State</span></span>|<span data-ttu-id="1079a-132">描述</span><span class="sxs-lookup"><span data-stu-id="1079a-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1079a-133">Aborted</span><span class="sxs-lookup"><span data-stu-id="1079a-133">Aborted</span></span>|<span data-ttu-id="1079a-134">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="1079a-134">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="1079a-135">已完成</span><span class="sxs-lookup"><span data-stu-id="1079a-135">Completed</span></span>|<span data-ttu-id="1079a-136">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="1079a-136">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="1079a-137">Deleted</span><span class="sxs-lookup"><span data-stu-id="1079a-137">Deleted</span></span>|<span data-ttu-id="1079a-138">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="1079a-138">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="1079a-139">Idle</span><span class="sxs-lookup"><span data-stu-id="1079a-139">Idle</span></span>|<span data-ttu-id="1079a-140">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="1079a-140">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="1079a-141">Persisted</span><span class="sxs-lookup"><span data-stu-id="1079a-141">Persisted</span></span>|<span data-ttu-id="1079a-142">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="1079a-142">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="1079a-143">Resumed</span><span class="sxs-lookup"><span data-stu-id="1079a-143">Resumed</span></span>|<span data-ttu-id="1079a-144">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="1079a-144">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="1079a-145">已开始</span><span class="sxs-lookup"><span data-stu-id="1079a-145">Started</span></span>|<span data-ttu-id="1079a-146">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="1079a-146">The workflow instance is started.</span></span>|  
|<span data-ttu-id="1079a-147">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="1079a-147">UnhandledException</span></span>|<span data-ttu-id="1079a-148">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="1079a-148">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="1079a-149">已卸载</span><span class="sxs-lookup"><span data-stu-id="1079a-149">Unloaded</span></span>|<span data-ttu-id="1079a-150">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="1079a-150">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="1079a-151">Canceled</span><span class="sxs-lookup"><span data-stu-id="1079a-151">Canceled</span></span>|<span data-ttu-id="1079a-152">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="1079a-152">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="1079a-153">挂起的</span><span class="sxs-lookup"><span data-stu-id="1079a-153">Suspended</span></span>|<span data-ttu-id="1079a-154">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="1079a-154">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="1079a-155">Terminated</span><span class="sxs-lookup"><span data-stu-id="1079a-155">Terminated</span></span>|<span data-ttu-id="1079a-156">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="1079a-156">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="1079a-157">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="1079a-157">Unsuspended</span></span>|<span data-ttu-id="1079a-158">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="1079a-158">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1079a-159">示例</span><span class="sxs-lookup"><span data-stu-id="1079a-159">Example</span></span>  
 <span data-ttu-id="1079a-160">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="1079a-160">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1079a-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="1079a-161">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1079a-162">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1079a-162">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1079a-163">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1079a-163">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
