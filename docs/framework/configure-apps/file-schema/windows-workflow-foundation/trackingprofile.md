---
title: '&lt;trackingProfile&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8ab3c0c30c193d176febbf832274a54b214b5458
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50047964"
---
# <a name="lttrackingprofilegt"></a><span data-ttu-id="b11a0-102">&lt;trackingProfile&gt;</span><span class="sxs-lookup"><span data-stu-id="b11a0-102">&lt;trackingProfile&gt;</span></span>
<span data-ttu-id="b11a0-103">表示用于创建工作流跟踪记录中跟踪参与者的订阅的配置节。</span><span class="sxs-lookup"><span data-stu-id="b11a0-103">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="b11a0-104">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅当工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="b11a0-104">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b11a0-105">跟踪配置文件节中定义的查询用于定义订阅返回的事件类型。</span><span class="sxs-lookup"><span data-stu-id="b11a0-105">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="b11a0-106">工作流跟踪和其配置的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)并[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b11a0-106">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b11a0-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b11a0-107">\<system.serviceModel></span></span>  
<span data-ttu-id="b11a0-108">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="b11a0-108">\<tracking></span></span>  
<span data-ttu-id="b11a0-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b11a0-109">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b11a0-110">语法</span><span class="sxs-lookup"><span data-stu-id="b11a0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b11a0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b11a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b11a0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b11a0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b11a0-113">特性</span><span class="sxs-lookup"><span data-stu-id="b11a0-113">Attributes</span></span>  
  
|<span data-ttu-id="b11a0-114">特性</span><span class="sxs-lookup"><span data-stu-id="b11a0-114">Attribute</span></span>|<span data-ttu-id="b11a0-115">描述</span><span class="sxs-lookup"><span data-stu-id="b11a0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b11a0-116">name</span><span class="sxs-lookup"><span data-stu-id="b11a0-116">name</span></span>|<span data-ttu-id="b11a0-117">一个字符串，指定跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b11a0-117">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b11a0-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b11a0-118">Child Elements</span></span>  
  
|<span data-ttu-id="b11a0-119">元素</span><span class="sxs-lookup"><span data-stu-id="b11a0-119">Element</span></span>|<span data-ttu-id="b11a0-120">描述</span><span class="sxs-lookup"><span data-stu-id="b11a0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b11a0-121">\<参与者 ></span><span class="sxs-lookup"><span data-stu-id="b11a0-121">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="b11a0-122">一个配置元素，包含 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="b11a0-122">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b11a0-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b11a0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b11a0-124">元素</span><span class="sxs-lookup"><span data-stu-id="b11a0-124">Element</span></span>|<span data-ttu-id="b11a0-125">描述</span><span class="sxs-lookup"><span data-stu-id="b11a0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b11a0-126">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="b11a0-126">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="b11a0-127">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="b11a0-127">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b11a0-128">备注</span><span class="sxs-lookup"><span data-stu-id="b11a0-128">Remarks</span></span>  
 <span data-ttu-id="b11a0-129">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅当工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="b11a0-129">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b11a0-130">根据您的监视要求，可以编写一个非常粗陋的配置文件，用来订阅对工作流进行的一小组高级状态更改。</span><span class="sxs-lookup"><span data-stu-id="b11a0-130">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="b11a0-131">相反，也可以创建一个非常具体的配置文件，其生成的事件足够丰富，可在以后重新构造详细的执行流。</span><span class="sxs-lookup"><span data-stu-id="b11a0-131">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="b11a0-132">跟踪配置文件组织为跟踪记录的声明性订阅，利用这些订阅可以查询特定跟踪记录的工作流运行时。</span><span class="sxs-lookup"><span data-stu-id="b11a0-132">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="b11a0-133">有少量的查询类型，可用于订阅的不同类<xref:System.Activities.Tracking.TrackingRecord>对象。</span><span class="sxs-lookup"><span data-stu-id="b11a0-133">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="b11a0-134">有关查询的完整列表，请参阅[\<参与者 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)并[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)...</span><span class="sxs-lookup"><span data-stu-id="b11a0-134">For a complete list of queries, see [\<participants>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) and [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="b11a0-135">下面的示例演示配置文件，跟踪参与者可订阅中的跟踪配置文件`Started`和`Completed`工作流事件。</span><span class="sxs-lookup"><span data-stu-id="b11a0-135">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b11a0-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="b11a0-136">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="b11a0-137">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b11a0-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b11a0-138">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b11a0-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
