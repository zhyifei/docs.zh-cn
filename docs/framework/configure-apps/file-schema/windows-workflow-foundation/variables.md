---
title: “变量”&lt;&gt;
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: c3861eb02d7b19bde6932c67c3d5d19b82fd8fcf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520527"
---
# <a name="ltvariablesgt"></a><span data-ttu-id="7d1b4-102">“变量”&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="7d1b4-102">&lt;variables&gt;</span></span>
<span data-ttu-id="7d1b4-103">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="7d1b4-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7d1b4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7d1b4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="7d1b4-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="7d1b4-106">\<tracking></span></span>  
<span data-ttu-id="7d1b4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7d1b4-107">\<trackingProfile></span></span>  
<span data-ttu-id="7d1b4-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7d1b4-108">\<workflow></span></span>  
<span data-ttu-id="7d1b4-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="7d1b4-109">\<activityStateQueries></span></span>  
<span data-ttu-id="7d1b4-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="7d1b4-110">\<activityStateQuery></span></span>  
<span data-ttu-id="7d1b4-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="7d1b4-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d1b4-112">语法</span><span class="sxs-lookup"><span data-stu-id="7d1b4-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d1b4-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7d1b4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7d1b4-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d1b4-115">特性</span><span class="sxs-lookup"><span data-stu-id="7d1b4-115">Attributes</span></span>  
 <span data-ttu-id="7d1b4-116">无。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7d1b4-117">子元素</span><span class="sxs-lookup"><span data-stu-id="7d1b4-117">Child Elements</span></span>  
  
|<span data-ttu-id="7d1b4-118">元素</span><span class="sxs-lookup"><span data-stu-id="7d1b4-118">Element</span></span>|<span data-ttu-id="7d1b4-119">描述</span><span class="sxs-lookup"><span data-stu-id="7d1b4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d1b4-120">\<variable></span><span class="sxs-lookup"><span data-stu-id="7d1b4-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="7d1b4-121">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7d1b4-122">父元素</span><span class="sxs-lookup"><span data-stu-id="7d1b4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7d1b4-123">元素</span><span class="sxs-lookup"><span data-stu-id="7d1b4-123">Element</span></span>|<span data-ttu-id="7d1b4-124">描述</span><span class="sxs-lookup"><span data-stu-id="7d1b4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d1b4-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="7d1b4-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="7d1b4-126">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7d1b4-127">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d1b4-128">备注</span><span class="sxs-lookup"><span data-stu-id="7d1b4-128">Remarks</span></span>  
 <span data-ttu-id="7d1b4-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="7d1b4-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="7d1b4-131">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="7d1b4-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="7d1b4-133">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="7d1b4-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d1b4-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d1b4-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7d1b4-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7d1b4-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7d1b4-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7d1b4-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
