---
title: <states> 的 <activityStateQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7cc2018-2b79-44f1-825a-bb7ca08690a3
ms.openlocfilehash: 97664518f7c7c0078cef1c81035724a02c9857c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368007"
---
# <a name="states-of-activitystatequery"></a><span data-ttu-id="2ba2e-102">\<状态 > 的\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="2ba2e-102">\<states> of \<activityStateQuery></span></span>
<span data-ttu-id="2ba2e-103">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-103">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="2ba2e-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="2ba2e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2ba2e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2ba2e-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2ba2e-106">\<tracking></span></span>  
<span data-ttu-id="2ba2e-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2ba2e-107">\<trackingProfile></span></span>  
<span data-ttu-id="2ba2e-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2ba2e-108">\<workflow></span></span>  
<span data-ttu-id="2ba2e-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="2ba2e-109">\<activityStateQueries></span></span>  
<span data-ttu-id="2ba2e-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2ba2e-110">\<activityStateQuery></span></span>  
<span data-ttu-id="2ba2e-111">\<states></span><span class="sxs-lookup"><span data-stu-id="2ba2e-111">\<states></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba2e-112">语法</span><span class="sxs-lookup"><span data-stu-id="2ba2e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ba2e-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2ba2e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="2ba2e-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ba2e-115">特性</span><span class="sxs-lookup"><span data-stu-id="2ba2e-115">Attributes</span></span>  
 <span data-ttu-id="2ba2e-116">无。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2ba2e-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2ba2e-117">Child Elements</span></span>  
  
|<span data-ttu-id="2ba2e-118">元素</span><span class="sxs-lookup"><span data-stu-id="2ba2e-118">Element</span></span>|<span data-ttu-id="2ba2e-119">描述</span><span class="sxs-lookup"><span data-stu-id="2ba2e-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ba2e-120">\<state></span><span class="sxs-lookup"><span data-stu-id="2ba2e-120">\<state></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/state-of-states.md)|<span data-ttu-id="2ba2e-121">一个配置元素，该元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-121">A configuration element that contains the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2ba2e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="2ba2e-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2ba2e-123">元素</span><span class="sxs-lookup"><span data-stu-id="2ba2e-123">Element</span></span>|<span data-ttu-id="2ba2e-124">描述</span><span class="sxs-lookup"><span data-stu-id="2ba2e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ba2e-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="2ba2e-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="2ba2e-126">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="2ba2e-127">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ba2e-128">备注</span><span class="sxs-lookup"><span data-stu-id="2ba2e-128">Remarks</span></span>  
 <span data-ttu-id="2ba2e-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="2ba2e-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="2ba2e-131">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="2ba2e-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="2ba2e-133">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="2ba2e-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2ba2e-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ba2e-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2ba2e-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2ba2e-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2ba2e-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="2ba2e-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
