---
title: <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 9f8c3e4f-e2e3-4402-9760-03bf918ece7b
ms.openlocfilehash: 539ce0ba72ae7a8d568cdea3a1a3aab3eec1001b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220729"
---
# <a name="activitystatequery"></a><span data-ttu-id="18d05-101">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="18d05-101">\<activityStateQuery></span></span>
<span data-ttu-id="18d05-102">表示一个查询，该查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="18d05-102">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="18d05-103">例如，你可能想要跟踪的每次在"发送电子邮件"活动完成工作流实例内。</span><span class="sxs-lookup"><span data-stu-id="18d05-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="18d05-104">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="18d05-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="18d05-105">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="18d05-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="18d05-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="18d05-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="18d05-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="18d05-107">\<system.serviceModel></span></span>  
<span data-ttu-id="18d05-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="18d05-108">\<tracking></span></span>  
<span data-ttu-id="18d05-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="18d05-109">\<trackingProfile></span></span>  
<span data-ttu-id="18d05-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="18d05-110">\<workflow></span></span>  
<span data-ttu-id="18d05-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="18d05-111">\<activityStateQueries></span></span>  
<span data-ttu-id="18d05-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="18d05-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18d05-113">语法</span><span class="sxs-lookup"><span data-stu-id="18d05-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18d05-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="18d05-114">Attributes and Elements</span></span>  
 <span data-ttu-id="18d05-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="18d05-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18d05-116">特性</span><span class="sxs-lookup"><span data-stu-id="18d05-116">Attributes</span></span>  
  
|<span data-ttu-id="18d05-117">特性</span><span class="sxs-lookup"><span data-stu-id="18d05-117">Attribute</span></span>|<span data-ttu-id="18d05-118">描述</span><span class="sxs-lookup"><span data-stu-id="18d05-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18d05-119">activityName</span><span class="sxs-lookup"><span data-stu-id="18d05-119">activityName</span></span>|<span data-ttu-id="18d05-120">一个字符串，指定要对其筛选 <xref:System.Activities.Tracking.ActivityStateRecord> 实例的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="18d05-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18d05-121">子元素</span><span class="sxs-lookup"><span data-stu-id="18d05-121">Child Elements</span></span>  
  
|<span data-ttu-id="18d05-122">元素</span><span class="sxs-lookup"><span data-stu-id="18d05-122">Element</span></span>|<span data-ttu-id="18d05-123">描述</span><span class="sxs-lookup"><span data-stu-id="18d05-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18d05-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="18d05-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="18d05-125">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="18d05-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="18d05-126">\<states></span><span class="sxs-lookup"><span data-stu-id="18d05-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="18d05-127">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="18d05-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="18d05-128">\<states></span><span class="sxs-lookup"><span data-stu-id="18d05-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="18d05-129">与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="18d05-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="18d05-130">父元素</span><span class="sxs-lookup"><span data-stu-id="18d05-130">Parent Elements</span></span>  
  
|<span data-ttu-id="18d05-131">元素</span><span class="sxs-lookup"><span data-stu-id="18d05-131">Element</span></span>|<span data-ttu-id="18d05-132">描述</span><span class="sxs-lookup"><span data-stu-id="18d05-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18d05-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="18d05-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="18d05-134">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="18d05-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="18d05-135">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="18d05-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18d05-136">备注</span><span class="sxs-lookup"><span data-stu-id="18d05-136">Remarks</span></span>  
 <span data-ttu-id="18d05-137">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="18d05-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="18d05-138">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="18d05-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="18d05-139">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="18d05-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="18d05-140">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="18d05-140">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="18d05-141">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="18d05-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="18d05-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="18d05-142">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="18d05-143">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="18d05-143">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="18d05-144">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="18d05-144">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
