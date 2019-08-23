---
title: <states> 的 <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 50827577374859133e6c673e8850e145b4ccab73
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947434"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="16474-102">\<activityStateQuery > 的\<状态 ></span><span class="sxs-lookup"><span data-stu-id="16474-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="16474-103">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="16474-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="16474-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="16474-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="16474-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="16474-105">\<system.serviceModel></span></span>  
<span data-ttu-id="16474-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="16474-106">\<tracking></span></span>  
<span data-ttu-id="16474-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="16474-107">\<trackingProfile></span></span>  
<span data-ttu-id="16474-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="16474-108">\<workflow></span></span>  
<span data-ttu-id="16474-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="16474-109">\<activityStateQueries></span></span>  
<span data-ttu-id="16474-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="16474-110">\<activityStateQuery></span></span>  
<span data-ttu-id="16474-111">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="16474-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16474-112">语法</span><span class="sxs-lookup"><span data-stu-id="16474-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16474-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="16474-113">Attributes and Elements</span></span>  
 <span data-ttu-id="16474-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="16474-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16474-115">特性</span><span class="sxs-lookup"><span data-stu-id="16474-115">Attributes</span></span>  
 <span data-ttu-id="16474-116">无。</span><span class="sxs-lookup"><span data-stu-id="16474-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="16474-117">子元素</span><span class="sxs-lookup"><span data-stu-id="16474-117">Child Elements</span></span>  
  
|<span data-ttu-id="16474-118">元素</span><span class="sxs-lookup"><span data-stu-id="16474-118">Element</span></span>|<span data-ttu-id="16474-119">描述</span><span class="sxs-lookup"><span data-stu-id="16474-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16474-120">\<state></span><span class="sxs-lookup"><span data-stu-id="16474-120">\<state></span></span>](state-of-states.md)|<span data-ttu-id="16474-121">一个配置元素，该元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="16474-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="16474-122">父元素</span><span class="sxs-lookup"><span data-stu-id="16474-122">Parent Elements</span></span>  
  
|<span data-ttu-id="16474-123">元素</span><span class="sxs-lookup"><span data-stu-id="16474-123">Element</span></span>|<span data-ttu-id="16474-124">描述</span><span class="sxs-lookup"><span data-stu-id="16474-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="16474-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="16474-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="16474-126">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="16474-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="16474-127">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="16474-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16474-128">备注</span><span class="sxs-lookup"><span data-stu-id="16474-128">Remarks</span></span>  
 <span data-ttu-id="16474-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="16474-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="16474-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="16474-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="16474-131">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="16474-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="16474-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="16474-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="16474-133">变量和参数只能通过 ActivityStateRecord 提取, 因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="16474-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="16474-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="16474-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="16474-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="16474-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="16474-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="16474-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
