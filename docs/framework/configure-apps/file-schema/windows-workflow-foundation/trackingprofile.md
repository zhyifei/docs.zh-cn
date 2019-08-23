---
title: <trackingProfile>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
ms.openlocfilehash: 8b8cfe95a646563642e7425fdb4b5257cafa466f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947302"
---
# <a name="trackingprofile"></a><span data-ttu-id="2ce62-101">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2ce62-101">\<trackingProfile></span></span>
<span data-ttu-id="2ce62-102">表示用于在跟踪参与者中创建工作流跟踪记录订阅的配置节。</span><span class="sxs-lookup"><span data-stu-id="2ce62-102">Represents a configuration section for creating a subscription to workflow tracking records in a tracking participant.</span></span> <span data-ttu-id="2ce62-103">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅当工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="2ce62-103">A tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="2ce62-104">跟踪配置文件节中定义的查询用于定义订阅返回的事件类型。</span><span class="sxs-lookup"><span data-stu-id="2ce62-104">The queries defined within the tracking profile section define the kinds of events that are returned by the subscription.</span></span>  
  
 <span data-ttu-id="2ce62-105">有关工作流跟踪及其配置的详细信息, 请参阅[工作流跟踪和跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)和[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce62-105">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2ce62-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ce62-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2ce62-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="2ce62-107">\<tracking></span></span>  
<span data-ttu-id="2ce62-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2ce62-108">\<trackingProfile></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce62-109">语法</span><span class="sxs-lookup"><span data-stu-id="2ce62-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ce62-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2ce62-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2ce62-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2ce62-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ce62-112">特性</span><span class="sxs-lookup"><span data-stu-id="2ce62-112">Attributes</span></span>  
  
|<span data-ttu-id="2ce62-113">特性</span><span class="sxs-lookup"><span data-stu-id="2ce62-113">Attribute</span></span>|<span data-ttu-id="2ce62-114">描述</span><span class="sxs-lookup"><span data-stu-id="2ce62-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ce62-115">NAME</span><span class="sxs-lookup"><span data-stu-id="2ce62-115">name</span></span>|<span data-ttu-id="2ce62-116">一个字符串，指定跟踪配置文件的名称。</span><span class="sxs-lookup"><span data-stu-id="2ce62-116">A string that specifies the name of the tracking profile.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ce62-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2ce62-117">Child Elements</span></span>  
  
|<span data-ttu-id="2ce62-118">元素</span><span class="sxs-lookup"><span data-stu-id="2ce62-118">Element</span></span>|<span data-ttu-id="2ce62-119">描述</span><span class="sxs-lookup"><span data-stu-id="2ce62-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce62-120">\<participants></span><span class="sxs-lookup"><span data-stu-id="2ce62-120">\<participants></span></span>](participants.md)|<span data-ttu-id="2ce62-121">一个配置元素，包含 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="2ce62-121">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId%2A?displayProperty=nameWithType> property.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ce62-122">父元素</span><span class="sxs-lookup"><span data-stu-id="2ce62-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2ce62-123">元素</span><span class="sxs-lookup"><span data-stu-id="2ce62-123">Element</span></span>|<span data-ttu-id="2ce62-124">描述</span><span class="sxs-lookup"><span data-stu-id="2ce62-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce62-125">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2ce62-125">\<tracking></span></span>](tracking.md)|<span data-ttu-id="2ce62-126">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="2ce62-126">Represents a configuration section for defining tracking settings for a workflow service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ce62-127">备注</span><span class="sxs-lookup"><span data-stu-id="2ce62-127">Remarks</span></span>  
 <span data-ttu-id="2ce62-128">跟踪配置文件包含跟踪查询，这些查询允许跟踪参与者订阅当工作流实例的状态在运行时发生更改时发出的工作流事件。</span><span class="sxs-lookup"><span data-stu-id="2ce62-128">Tracking profiles contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="2ce62-129">根据您的监视需求，可以编写一个非常粗陋的配置文件，用来订阅对工作流进行的一小组高级状态更改。</span><span class="sxs-lookup"><span data-stu-id="2ce62-129">Depending on your monitoring requirements you may write a profile that is very coarse, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="2ce62-130">相反，也可以创建一个非常具体的配置文件，其生成的事件足够丰富，可在以后重新构造详细的执行流。</span><span class="sxs-lookup"><span data-stu-id="2ce62-130">Conversely, you may create a very specific profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="2ce62-131">跟踪配置文件组织为跟踪记录的声明性订阅，利用这些订阅可以查询特定跟踪记录的工作流运行时。</span><span class="sxs-lookup"><span data-stu-id="2ce62-131">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="2ce62-132">有几种查询类型允许您订阅不同的<xref:System.Activities.Tracking.TrackingRecord>对象类。</span><span class="sxs-lookup"><span data-stu-id="2ce62-132">There are a handful of query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="2ce62-133">有关查询的完整列表, 请参阅[ \<参与者 >](participants.md)和[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="2ce62-133">For a complete list of queries, see [\<participants>](participants.md) and [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)..</span></span>  
  
 <span data-ttu-id="2ce62-134">下面的示例演示配置文件中的跟踪配置文件, 该配置文件允许跟踪参与者订阅`Started`和`Completed`工作流事件。</span><span class="sxs-lookup"><span data-stu-id="2ce62-134">The following example shows a tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ce62-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ce62-135">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="2ce62-136">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2ce62-136">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2ce62-137">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="2ce62-137">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
