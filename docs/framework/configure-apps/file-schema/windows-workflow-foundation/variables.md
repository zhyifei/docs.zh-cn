---
title: “变量”&lt;&gt;
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: da0fd144-dda9-4613-b650-fe6325076513
ms.openlocfilehash: d0dc83951bdf894d0061971ae4b79854a7c8bcd8
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltvariablesgt"></a><span data-ttu-id="a6d4d-102">“变量”&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="a6d4d-102">&lt;variables&gt;</span></span>
<span data-ttu-id="a6d4d-103">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="a6d4d-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a6d4d-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a6d4d-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a6d4d-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-106">\<tracking></span></span>  
<span data-ttu-id="a6d4d-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a6d4d-107">\<trackingProfile></span></span>  
<span data-ttu-id="a6d4d-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-108">\<workflow></span></span>  
<span data-ttu-id="a6d4d-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-109">\<activityStateQueries></span></span>  
<span data-ttu-id="a6d4d-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-110">\<activityStateQuery></span></span>  
<span data-ttu-id="a6d4d-111">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-111">\<variables></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6d4d-112">语法</span><span class="sxs-lookup"><span data-stu-id="a6d4d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6d4d-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a6d4d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a6d4d-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6d4d-115">特性</span><span class="sxs-lookup"><span data-stu-id="a6d4d-115">Attributes</span></span>  
 <span data-ttu-id="a6d4d-116">无。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a6d4d-117">子元素</span><span class="sxs-lookup"><span data-stu-id="a6d4d-117">Child Elements</span></span>  
  
|<span data-ttu-id="a6d4d-118">元素</span><span class="sxs-lookup"><span data-stu-id="a6d4d-118">Element</span></span>|<span data-ttu-id="a6d4d-119">描述</span><span class="sxs-lookup"><span data-stu-id="a6d4d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6d4d-120">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-120">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="a6d4d-121">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-121">A variable associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6d4d-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a6d4d-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a6d4d-123">元素</span><span class="sxs-lookup"><span data-stu-id="a6d4d-123">Element</span></span>|<span data-ttu-id="a6d4d-124">描述</span><span class="sxs-lookup"><span data-stu-id="a6d4d-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6d4d-125">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="a6d4d-125">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="a6d4d-126">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a6d4d-127">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6d4d-128">备注</span><span class="sxs-lookup"><span data-stu-id="a6d4d-128">Remarks</span></span>  
 <span data-ttu-id="a6d4d-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a6d4d-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a6d4d-131">你可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)和[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或自变量从工作流中的任何活动。下面的示例演示提取变量和自变量的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a6d4d-132">变量和自变量只能使用 ActivityStateRecord 来提取，并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="a6d4d-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6d4d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6d4d-133">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a6d4d-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="a6d4d-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a6d4d-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a6d4d-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
