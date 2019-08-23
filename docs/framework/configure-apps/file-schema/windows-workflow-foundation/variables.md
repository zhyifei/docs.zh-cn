---
title: <variables>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: 563ce96f61bbb39f1590ca0f43c163ea2d3d7961
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947244"
---
# <a name="variables"></a><span data-ttu-id="6c965-101">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="6c965-101">\<variables></span></span>
<span data-ttu-id="6c965-102">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="6c965-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="6c965-103">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6c965-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6c965-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6c965-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6c965-105">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="6c965-105">\<tracking></span></span>  
<span data-ttu-id="6c965-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6c965-106">\<trackingProfile></span></span>  
<span data-ttu-id="6c965-107">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="6c965-107">\<workflow></span></span>  
<span data-ttu-id="6c965-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6c965-108">\<activityStateQueries></span></span>  
<span data-ttu-id="6c965-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6c965-109">\<activityStateQuery></span></span>  
<span data-ttu-id="6c965-110">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="6c965-110">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c965-111">语法</span><span class="sxs-lookup"><span data-stu-id="6c965-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6c965-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6c965-112">Attributes and Elements</span></span>  
 <span data-ttu-id="6c965-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6c965-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6c965-114">特性</span><span class="sxs-lookup"><span data-stu-id="6c965-114">Attributes</span></span>  
 <span data-ttu-id="6c965-115">无。</span><span class="sxs-lookup"><span data-stu-id="6c965-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6c965-116">子元素</span><span class="sxs-lookup"><span data-stu-id="6c965-116">Child Elements</span></span>  
  
|<span data-ttu-id="6c965-117">元素</span><span class="sxs-lookup"><span data-stu-id="6c965-117">Element</span></span>|<span data-ttu-id="6c965-118">描述</span><span class="sxs-lookup"><span data-stu-id="6c965-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c965-119">\<variable></span><span class="sxs-lookup"><span data-stu-id="6c965-119">\<variable></span></span>](variable.md)|<span data-ttu-id="6c965-120">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="6c965-120">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6c965-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6c965-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6c965-122">元素</span><span class="sxs-lookup"><span data-stu-id="6c965-122">Element</span></span>|<span data-ttu-id="6c965-123">描述</span><span class="sxs-lookup"><span data-stu-id="6c965-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6c965-124">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6c965-124">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="6c965-125">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="6c965-125">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6c965-126">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="6c965-126">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c965-127">备注</span><span class="sxs-lookup"><span data-stu-id="6c965-127">Remarks</span></span>  
 <span data-ttu-id="6c965-128">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="6c965-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6c965-129">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="6c965-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6c965-130">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="6c965-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="6c965-131">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="6c965-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6c965-132">变量和参数只能通过 ActivityStateRecord 提取, 因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="6c965-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6c965-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c965-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6c965-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6c965-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c965-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6c965-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
