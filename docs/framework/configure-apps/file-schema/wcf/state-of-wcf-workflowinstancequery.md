---
title: <state>WCF，<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: 40f21055-766c-4be9-86c4-d1d899007098
ms.openlocfilehash: 80f7532f3c51680a2e34713b526dc43822db61b9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854960"
---
# <a name="state-of-wcf-workflowinstancequery"></a><span data-ttu-id="9380f-102">\<WCF \<> 状态 ></span><span class="sxs-lookup"><span data-stu-id="9380f-102">\<state> of WCF, \<workflowInstanceQuery></span></span>
<span data-ttu-id="9380f-103">表示创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="9380f-103">Represents a collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>  
  
 <span data-ttu-id="9380f-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9380f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9380f-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9380f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="9380f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="9380f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="9380f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="9380f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="9380f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Workflowinstancequeries&gt; >** ](workflowinstancequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQueries>**](workflowinstancequeries-of-wcf.md)</span></span>\
<span data-ttu-id="9380f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<workflowInstanceQuery >** ](workflowinstancequery-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflowInstanceQuery>**](workflowinstancequery-of-wcf.md)</span></span>\
<span data-ttu-id="9380f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<状态 >** ](states-of-wcf-workflowinstancequery.md)</span><span class="sxs-lookup"><span data-stu-id="9380f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<states>**](states-of-wcf-workflowinstancequery.md)</span></span>\
<span data-ttu-id="9380f-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<状态 >**</span><span class="sxs-lookup"><span data-stu-id="9380f-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<state>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9380f-115">语法</span><span class="sxs-lookup"><span data-stu-id="9380f-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9380f-116">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9380f-116">Attributes and elements</span></span>

<span data-ttu-id="9380f-117">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9380f-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="9380f-118">特性</span><span class="sxs-lookup"><span data-stu-id="9380f-118">Attributes</span></span>

|<span data-ttu-id="9380f-119">特性</span><span class="sxs-lookup"><span data-stu-id="9380f-119">Attribute</span></span>|<span data-ttu-id="9380f-120">描述</span><span class="sxs-lookup"><span data-stu-id="9380f-120">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9380f-121">一个字符串，指定创建跟踪记录时已跟踪工作流实例中的已订阅状态。</span><span class="sxs-lookup"><span data-stu-id="9380f-121">A string that specifies a subscribed state from the tracked workflow instance when the tracking record is created.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9380f-122">子元素</span><span class="sxs-lookup"><span data-stu-id="9380f-122">Child elements</span></span>

<span data-ttu-id="9380f-123">无。</span><span class="sxs-lookup"><span data-stu-id="9380f-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9380f-124">父元素</span><span class="sxs-lookup"><span data-stu-id="9380f-124">Parent elements</span></span>

|<span data-ttu-id="9380f-125">元素</span><span class="sxs-lookup"><span data-stu-id="9380f-125">Element</span></span>|<span data-ttu-id="9380f-126">描述</span><span class="sxs-lookup"><span data-stu-id="9380f-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9380f-127">\<states></span><span class="sxs-lookup"><span data-stu-id="9380f-127">\<states></span></span>](states-of-wcf-workflowinstancequery.md)|<span data-ttu-id="9380f-128">创建跟踪记录时已跟踪工作流实例中已订阅状态的集合。</span><span class="sxs-lookup"><span data-stu-id="9380f-128">A collection of subscribed states from the tracked workflow instance when the tracking records are created.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9380f-129">备注</span><span class="sxs-lookup"><span data-stu-id="9380f-129">Remarks</span></span>  

<span data-ttu-id="9380f-130">返回的记录由此集合中的状态进行筛选。</span><span class="sxs-lookup"><span data-stu-id="9380f-130">The returned records are filtered by the states in this collection.</span></span>  
  
<span data-ttu-id="9380f-131">下表描述了可能的状态值：</span><span class="sxs-lookup"><span data-stu-id="9380f-131">Possible state values are described in the following table:</span></span>
  
|<span data-ttu-id="9380f-132">状态</span><span class="sxs-lookup"><span data-stu-id="9380f-132">State</span></span>|<span data-ttu-id="9380f-133">描述</span><span class="sxs-lookup"><span data-stu-id="9380f-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9380f-134">Aborted</span><span class="sxs-lookup"><span data-stu-id="9380f-134">Aborted</span></span>|<span data-ttu-id="9380f-135">工作流实例已中止。</span><span class="sxs-lookup"><span data-stu-id="9380f-135">The workflow instance is aborted.</span></span>|  
|<span data-ttu-id="9380f-136">已完成</span><span class="sxs-lookup"><span data-stu-id="9380f-136">Completed</span></span>|<span data-ttu-id="9380f-137">工作流实例已完成。</span><span class="sxs-lookup"><span data-stu-id="9380f-137">The workflow instance is completed.</span></span>|  
|<span data-ttu-id="9380f-138">Deleted</span><span class="sxs-lookup"><span data-stu-id="9380f-138">Deleted</span></span>|<span data-ttu-id="9380f-139">工作流实例已删除。</span><span class="sxs-lookup"><span data-stu-id="9380f-139">The workflow instance is deleted.</span></span>|  
|<span data-ttu-id="9380f-140">Idle</span><span class="sxs-lookup"><span data-stu-id="9380f-140">Idle</span></span>|<span data-ttu-id="9380f-141">工作流实例处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="9380f-141">The workflow instance is idle.</span></span>|  
|<span data-ttu-id="9380f-142">Persisted</span><span class="sxs-lookup"><span data-stu-id="9380f-142">Persisted</span></span>|<span data-ttu-id="9380f-143">工作流实例已保留。</span><span class="sxs-lookup"><span data-stu-id="9380f-143">The workflow instance is persisted.</span></span>|  
|<span data-ttu-id="9380f-144">Resumed</span><span class="sxs-lookup"><span data-stu-id="9380f-144">Resumed</span></span>|<span data-ttu-id="9380f-145">工作流实例已恢复。</span><span class="sxs-lookup"><span data-stu-id="9380f-145">The workflow instance is resumed.</span></span>|  
|<span data-ttu-id="9380f-146">已开始</span><span class="sxs-lookup"><span data-stu-id="9380f-146">Started</span></span>|<span data-ttu-id="9380f-147">工作流实例已启动。</span><span class="sxs-lookup"><span data-stu-id="9380f-147">The workflow instance is started.</span></span>|  
|<span data-ttu-id="9380f-148">UnhandledException</span><span class="sxs-lookup"><span data-stu-id="9380f-148">UnhandledException</span></span>|<span data-ttu-id="9380f-149">工作流实例遇到了未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="9380f-149">The workflow instance encountered an unhandled exception.</span></span>|  
|<span data-ttu-id="9380f-150">已卸载</span><span class="sxs-lookup"><span data-stu-id="9380f-150">Unloaded</span></span>|<span data-ttu-id="9380f-151">工作流实例已卸载。</span><span class="sxs-lookup"><span data-stu-id="9380f-151">The workflow instance is unloaded.</span></span>|  
|<span data-ttu-id="9380f-152">Canceled</span><span class="sxs-lookup"><span data-stu-id="9380f-152">Canceled</span></span>|<span data-ttu-id="9380f-153">工作流实例已取消。</span><span class="sxs-lookup"><span data-stu-id="9380f-153">The workflow instance is canceled.</span></span>|  
|<span data-ttu-id="9380f-154">挂起的</span><span class="sxs-lookup"><span data-stu-id="9380f-154">Suspended</span></span>|<span data-ttu-id="9380f-155">工作流实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="9380f-155">The workflow instance is suspended.</span></span>|  
|<span data-ttu-id="9380f-156">Terminated</span><span class="sxs-lookup"><span data-stu-id="9380f-156">Terminated</span></span>|<span data-ttu-id="9380f-157">工作流实例已终止。</span><span class="sxs-lookup"><span data-stu-id="9380f-157">The workflow instance is terminated.</span></span>|  
|<span data-ttu-id="9380f-158">Unsuspended</span><span class="sxs-lookup"><span data-stu-id="9380f-158">Unsuspended</span></span>|<span data-ttu-id="9380f-159">工作流实例已取消挂起。</span><span class="sxs-lookup"><span data-stu-id="9380f-159">The workflow instance is unsuspended.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9380f-160">示例</span><span class="sxs-lookup"><span data-stu-id="9380f-160">Example</span></span>

<span data-ttu-id="9380f-161">下面的配置使用此查询订阅 `Started` 实例状态的工作流实例级跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9380f-161">The following configuration subscribes to workflow instance-level tracking records for the `Started` instance state using this query.</span></span>  
  
```xml  
<workflowInstanceQueries>
  <workflowInstanceQuery>
    <states>
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a><span data-ttu-id="9380f-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="9380f-162">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9380f-163">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9380f-163">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9380f-164">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9380f-164">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
