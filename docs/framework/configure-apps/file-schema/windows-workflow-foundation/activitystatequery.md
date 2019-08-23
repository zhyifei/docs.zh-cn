---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 560df771b44fc8ba8d192657677bf0496283b539
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945432"
---
# <a name="activitystatequery"></a><span data-ttu-id="67e50-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="67e50-101">\<activityStateQuery></span></span>
<span data-ttu-id="67e50-102">表示一个查询，该查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="67e50-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="67e50-103">例如, 你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。</span><span class="sxs-lookup"><span data-stu-id="67e50-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="67e50-104">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="67e50-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="67e50-105">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="67e50-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="67e50-106">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="67e50-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="67e50-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="67e50-107">\<system.serviceModel></span></span>  
<span data-ttu-id="67e50-108">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="67e50-108">\<tracking></span></span>  
<span data-ttu-id="67e50-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="67e50-109">\<trackingProfile></span></span>  
<span data-ttu-id="67e50-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="67e50-110">\<workflow></span></span>  
<span data-ttu-id="67e50-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="67e50-111">\<activityStateQueries></span></span>  
<span data-ttu-id="67e50-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="67e50-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67e50-113">语法</span><span class="sxs-lookup"><span data-stu-id="67e50-113">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
        <states>
          <state name="String"/>
        </states>
        <variables>
          <variable name="String"/>
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67e50-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="67e50-114">Attributes and Elements</span></span>  
 <span data-ttu-id="67e50-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="67e50-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67e50-116">特性</span><span class="sxs-lookup"><span data-stu-id="67e50-116">Attributes</span></span>  
  
|<span data-ttu-id="67e50-117">特性</span><span class="sxs-lookup"><span data-stu-id="67e50-117">Attribute</span></span>|<span data-ttu-id="67e50-118">描述</span><span class="sxs-lookup"><span data-stu-id="67e50-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67e50-119">activityName</span><span class="sxs-lookup"><span data-stu-id="67e50-119">activityName</span></span>|<span data-ttu-id="67e50-120">一个字符串，指定要对其筛选 <xref:System.Activities.Tracking.ActivityStateRecord> 实例的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="67e50-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67e50-121">子元素</span><span class="sxs-lookup"><span data-stu-id="67e50-121">Child Elements</span></span>  
  
|<span data-ttu-id="67e50-122">元素</span><span class="sxs-lookup"><span data-stu-id="67e50-122">Element</span></span>|<span data-ttu-id="67e50-123">描述</span><span class="sxs-lookup"><span data-stu-id="67e50-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67e50-124">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="67e50-124">\<arguments></span></span>](arguments.md)|<span data-ttu-id="67e50-125">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="67e50-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="67e50-126">\<states></span><span class="sxs-lookup"><span data-stu-id="67e50-126">\<states></span></span>](states.md)|<span data-ttu-id="67e50-127">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="67e50-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="67e50-128">\<states></span><span class="sxs-lookup"><span data-stu-id="67e50-128">\<states></span></span>](states.md)|<span data-ttu-id="67e50-129">与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="67e50-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67e50-130">父元素</span><span class="sxs-lookup"><span data-stu-id="67e50-130">Parent Elements</span></span>  
  
|<span data-ttu-id="67e50-131">元素</span><span class="sxs-lookup"><span data-stu-id="67e50-131">Element</span></span>|<span data-ttu-id="67e50-132">描述</span><span class="sxs-lookup"><span data-stu-id="67e50-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67e50-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="67e50-133">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="67e50-134">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="67e50-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="67e50-135">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="67e50-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67e50-136">备注</span><span class="sxs-lookup"><span data-stu-id="67e50-136">Remarks</span></span>  
 <span data-ttu-id="67e50-137">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="67e50-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="67e50-138">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="67e50-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="67e50-139">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="67e50-139">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="67e50-140">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="67e50-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="67e50-141">变量和参数只能通过 ActivityStateRecord 提取, 因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="67e50-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="67e50-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="67e50-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="67e50-143">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="67e50-143">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="67e50-144">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="67e50-144">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
