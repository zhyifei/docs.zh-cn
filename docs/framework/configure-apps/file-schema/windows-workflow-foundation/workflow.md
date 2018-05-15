---
title: '&lt;工作流&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 560aa9b6-9cf3-460e-b798-f87d14b1d2de
ms.openlocfilehash: dc7c693fb2d8b47c0b968eb51cc59327fe43bcc0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltworkflowgt"></a><span data-ttu-id="e5d32-102">&lt;工作流&gt;</span><span class="sxs-lookup"><span data-stu-id="e5d32-102">&lt;workflow&gt;</span></span>
<span data-ttu-id="e5d32-103">一个配置元素，包含由标识的特定工作流的所有查询**超链接"http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx"ctivityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="e5d32-103">A configuration element that contains all queries for a specific workflow identified by the **a HYPERLINK "http://msdn.microsoft.com/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId** property.</span></span>  
  
 <span data-ttu-id="e5d32-104">在工作流跟踪和其配置的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)和[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d32-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="e5d32-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e5d32-105">\<system.serviceModel></span></span>  
<span data-ttu-id="e5d32-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e5d32-106">\<tracking></span></span>  
<span data-ttu-id="e5d32-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e5d32-107">\<trackingProfile></span></span>  
<span data-ttu-id="e5d32-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e5d32-108">\<workflow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d32-109">语法</span><span class="sxs-lookup"><span data-stu-id="e5d32-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5d32-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e5d32-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e5d32-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e5d32-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5d32-112">特性</span><span class="sxs-lookup"><span data-stu-id="e5d32-112">Attributes</span></span>  
  
|<span data-ttu-id="e5d32-113">特性</span><span class="sxs-lookup"><span data-stu-id="e5d32-113">Attribute</span></span>|<span data-ttu-id="e5d32-114">描述</span><span class="sxs-lookup"><span data-stu-id="e5d32-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5d32-115">activityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="e5d32-115">activityDefinitionId</span></span>|<span data-ttu-id="e5d32-116">一个字符串，指定所跟踪的工作流的活动定义 ID。</span><span class="sxs-lookup"><span data-stu-id="e5d32-116">A string that specifies the activity definition ID of the workflow being tracked.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5d32-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e5d32-117">Child Elements</span></span>  
  
|<span data-ttu-id="e5d32-118">元素</span><span class="sxs-lookup"><span data-stu-id="e5d32-118">Element</span></span>|<span data-ttu-id="e5d32-119">描述</span><span class="sxs-lookup"><span data-stu-id="e5d32-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5d32-120">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-120">\<activityScheduledQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledqueries.md)|<span data-ttu-id="e5d32-121">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="e5d32-121">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="e5d32-122">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="e5d32-122">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>|  
|[<span data-ttu-id="e5d32-123">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-123">\<activityStateQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequeries.md)|<span data-ttu-id="e5d32-124">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="e5d32-124">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="e5d32-125">例如，你可能想要跟踪的每次完成工作流实例中的"发送电子邮件"活动。</span><span class="sxs-lookup"><span data-stu-id="e5d32-125">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="e5d32-126">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="e5d32-126">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="e5d32-127">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="e5d32-127">The available states to subscribe to are specified in ActivityStates.</span></span>|  
|[<span data-ttu-id="e5d32-128">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-128">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="e5d32-129">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="e5d32-129">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e5d32-130">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="e5d32-130">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
|[<span data-ttu-id="e5d32-131">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-131">\<cancelRequestedQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedqueries.md)|<span data-ttu-id="e5d32-132">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="e5d32-132">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e5d32-133">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="e5d32-133">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
|[<span data-ttu-id="e5d32-134">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-134">\<customTrackingQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingqueries.md)|<span data-ttu-id="e5d32-135">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e5d32-135">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e5d32-136">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="e5d32-136">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>|  
|[<span data-ttu-id="e5d32-137">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-137">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="e5d32-138">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="e5d32-138">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="e5d32-139">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="e5d32-139">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="e5d32-140">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="e5d32-140">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="e5d32-141">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="e5d32-141">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>|  
|[<span data-ttu-id="e5d32-142">\<workflowInstanceQueries></span><span class="sxs-lookup"><span data-stu-id="e5d32-142">\<workflowInstanceQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequeries.md)|<span data-ttu-id="e5d32-143">表示配置元素的集合，这些配置元素跟踪工作流实例生命周期的更改，例如已开始或已完成的事件。</span><span class="sxs-lookup"><span data-stu-id="e5d32-143">Represents a collection of configuration elements that track workflow instance life cycle changes such as a started or completed event.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5d32-144">父元素</span><span class="sxs-lookup"><span data-stu-id="e5d32-144">Parent Elements</span></span>  
  
|<span data-ttu-id="e5d32-145">元素</span><span class="sxs-lookup"><span data-stu-id="e5d32-145">Element</span></span>|<span data-ttu-id="e5d32-146">描述</span><span class="sxs-lookup"><span data-stu-id="e5d32-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5d32-147">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e5d32-147">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="e5d32-148">表示一个配置节，用于创建工作流跟踪记录中的跟踪参与者的订阅。</span><span class="sxs-lookup"><span data-stu-id="e5d32-148">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="e5d32-149">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅当工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="e5d32-149">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="e5d32-150">跟踪配置文件节中定义的查询用于定义订阅返回的事件类型。</span><span class="sxs-lookup"><span data-stu-id="e5d32-150">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5d32-151">备注</span><span class="sxs-lookup"><span data-stu-id="e5d32-151">Remarks</span></span>  
 <span data-ttu-id="e5d32-152">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅当特定工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="e5d32-152">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a particular workflow instance changes at runtime.</span></span> <span data-ttu-id="e5d32-153">所跟踪的工作流实例由此配置元素来标识。</span><span class="sxs-lookup"><span data-stu-id="e5d32-153">The workflow instance being tracked is identified by this configuration element.</span></span>  
  
 <span data-ttu-id="e5d32-154">根据您的监视要求，可以编写一个非常粗陋的配置文件，用来订阅对工作流进行的一小组高级状态更改。</span><span class="sxs-lookup"><span data-stu-id="e5d32-154">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="e5d32-155">相反，也可以创建一个非常具体的配置文件，其生成的事件足够丰富，可在以后重新构造详细的执行流。</span><span class="sxs-lookup"><span data-stu-id="e5d32-155">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="e5d32-156">跟踪配置文件组织为跟踪记录的声明性订阅，利用这些订阅可以查询特定跟踪记录的工作流运行时。</span><span class="sxs-lookup"><span data-stu-id="e5d32-156">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="e5d32-157">有几种允许你订阅的跟踪记录的不同类的查询类型。</span><span class="sxs-lookup"><span data-stu-id="e5d32-157">There are a handful of query types that allow you subscribe to different classes of tracking records.</span></span> <span data-ttu-id="e5d32-158">有关查询的完整列表，请参阅本主题的子元素列表和[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="e5d32-158">For a complete list of queries, see the child element list of this topic and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="e5d32-159">下面的示例演示配置文件，跟踪参与者可订阅中的跟踪配置文件`Started`和`Completed`工作流事件。</span><span class="sxs-lookup"><span data-stu-id="e5d32-159">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e5d32-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5d32-160">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="e5d32-161">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e5d32-161">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e5d32-162">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e5d32-162">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
