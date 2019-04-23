---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: 2b0d982997ab590ce7f0fc4c482b1ddfa6bc758f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152797"
---
# <a name="arguments"></a><span data-ttu-id="97675-101">\<自变量 ></span><span class="sxs-lookup"><span data-stu-id="97675-101">\<arguments></span></span>
<span data-ttu-id="97675-102">表示与某一活动状态查询关联的参数的集合。</span><span class="sxs-lookup"><span data-stu-id="97675-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="97675-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="97675-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="97675-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="97675-104">\<system.serviceModel></span></span>  
<span data-ttu-id="97675-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="97675-105">\<tracking></span></span>  
<span data-ttu-id="97675-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="97675-106">\<trackingProfile></span></span>  
<span data-ttu-id="97675-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="97675-107">\<workflow></span></span>  
<span data-ttu-id="97675-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="97675-108">\<activityStateQueries></span></span>  
<span data-ttu-id="97675-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="97675-109">\<activityStateQuery></span></span>  
<span data-ttu-id="97675-110">\<自变量 ></span><span class="sxs-lookup"><span data-stu-id="97675-110">\<arguments></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97675-111">语法</span><span class="sxs-lookup"><span data-stu-id="97675-111">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97675-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="97675-112">Attributes and Elements</span></span>  
 <span data-ttu-id="97675-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="97675-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97675-114">特性</span><span class="sxs-lookup"><span data-stu-id="97675-114">Attributes</span></span>  
 <span data-ttu-id="97675-115">无。</span><span class="sxs-lookup"><span data-stu-id="97675-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="97675-116">子元素</span><span class="sxs-lookup"><span data-stu-id="97675-116">Child Elements</span></span>  
  
|<span data-ttu-id="97675-117">元素</span><span class="sxs-lookup"><span data-stu-id="97675-117">Element</span></span>|<span data-ttu-id="97675-118">描述</span><span class="sxs-lookup"><span data-stu-id="97675-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97675-119">\<argument></span><span class="sxs-lookup"><span data-stu-id="97675-119">\<argument></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/argument.md)|<span data-ttu-id="97675-120">与活动状态查询相关联的参数。</span><span class="sxs-lookup"><span data-stu-id="97675-120">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="97675-121">父元素</span><span class="sxs-lookup"><span data-stu-id="97675-121">Parent Elements</span></span>  
  
|<span data-ttu-id="97675-122">元素</span><span class="sxs-lookup"><span data-stu-id="97675-122">Element</span></span>|<span data-ttu-id="97675-123">描述</span><span class="sxs-lookup"><span data-stu-id="97675-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97675-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="97675-124">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="97675-125">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="97675-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="97675-126">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="97675-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97675-127">备注</span><span class="sxs-lookup"><span data-stu-id="97675-127">Remarks</span></span>  
 <span data-ttu-id="97675-128">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="97675-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="97675-129">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="97675-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="97675-130">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="97675-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="97675-131">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="97675-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="97675-132">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="97675-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97675-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="97675-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="97675-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="97675-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="97675-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="97675-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
