---
title: '&lt;states&gt; 的 &lt;state&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
ms.openlocfilehash: 1ddf7e0ed2849764f3b21e8cf1c31d98762c0d5e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54696238"
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="51cde-102">&lt;states&gt; 的 &lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="51cde-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="51cde-103">一个配置元素，该元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="51cde-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="51cde-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="51cde-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="51cde-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="51cde-105">\<system.serviceModel></span></span>  
<span data-ttu-id="51cde-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="51cde-106">\<tracking></span></span>  
<span data-ttu-id="51cde-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="51cde-107">\<trackingProfile></span></span>  
<span data-ttu-id="51cde-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="51cde-108">\<workflow></span></span>  
<span data-ttu-id="51cde-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="51cde-109">\<activityStateQueries></span></span>  
<span data-ttu-id="51cde-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="51cde-110">\<activityStateQuery></span></span>  
<span data-ttu-id="51cde-111">\<states></span><span class="sxs-lookup"><span data-stu-id="51cde-111">\<states></span></span>  
<span data-ttu-id="51cde-112">\<state></span><span class="sxs-lookup"><span data-stu-id="51cde-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51cde-113">语法</span><span class="sxs-lookup"><span data-stu-id="51cde-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="51cde-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="51cde-114">Attributes and Elements</span></span>  
 <span data-ttu-id="51cde-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="51cde-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="51cde-116">特性</span><span class="sxs-lookup"><span data-stu-id="51cde-116">Attributes</span></span>  
  
|<span data-ttu-id="51cde-117">特性</span><span class="sxs-lookup"><span data-stu-id="51cde-117">Attribute</span></span>|<span data-ttu-id="51cde-118">描述</span><span class="sxs-lookup"><span data-stu-id="51cde-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="51cde-119">name</span><span class="sxs-lookup"><span data-stu-id="51cde-119">name</span></span>|<span data-ttu-id="51cde-120">一个字符串，指定应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="51cde-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="51cde-121">子元素</span><span class="sxs-lookup"><span data-stu-id="51cde-121">Child Elements</span></span>  
 <span data-ttu-id="51cde-122">无。</span><span class="sxs-lookup"><span data-stu-id="51cde-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="51cde-123">父元素</span><span class="sxs-lookup"><span data-stu-id="51cde-123">Parent Elements</span></span>  
  
|<span data-ttu-id="51cde-124">元素</span><span class="sxs-lookup"><span data-stu-id="51cde-124">Element</span></span>|<span data-ttu-id="51cde-125">描述</span><span class="sxs-lookup"><span data-stu-id="51cde-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="51cde-126">\<states></span><span class="sxs-lookup"><span data-stu-id="51cde-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="51cde-127">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="51cde-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51cde-128">备注</span><span class="sxs-lookup"><span data-stu-id="51cde-128">Remarks</span></span>  
 <span data-ttu-id="51cde-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="51cde-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="51cde-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="51cde-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="51cde-131">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="51cde-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="51cde-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="51cde-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="51cde-133">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="51cde-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="51cde-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="51cde-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="51cde-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="51cde-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="51cde-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="51cde-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
