---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: f2aeb61e2e72f5bd6a696c031279f2c57907166b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946153"
---
# <a name="argument"></a><span data-ttu-id="a62d4-101">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="a62d4-101">\<argument></span></span>
<span data-ttu-id="a62d4-102">一个配置元素，表示与某一活动状态查询关联的参数。</span><span class="sxs-lookup"><span data-stu-id="a62d4-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="a62d4-103">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a62d4-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="a62d4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a62d4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a62d4-105">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="a62d4-105">\<tracking></span></span>  
<span data-ttu-id="a62d4-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a62d4-106">\<trackingProfile></span></span>  
<span data-ttu-id="a62d4-107">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="a62d4-107">\<workflow></span></span>  
<span data-ttu-id="a62d4-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="a62d4-108">\<activityStateQueries></span></span>  
<span data-ttu-id="a62d4-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="a62d4-109">\<activityStateQuery></span></span>  
<span data-ttu-id="a62d4-110">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="a62d4-110">\<arguments></span></span>  
<span data-ttu-id="a62d4-111">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="a62d4-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62d4-112">语法</span><span class="sxs-lookup"><span data-stu-id="a62d4-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a62d4-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a62d4-113">Attributes and Elements</span></span>  
 <span data-ttu-id="a62d4-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a62d4-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a62d4-115">特性</span><span class="sxs-lookup"><span data-stu-id="a62d4-115">Attributes</span></span>  
  
|<span data-ttu-id="a62d4-116">特性</span><span class="sxs-lookup"><span data-stu-id="a62d4-116">Attribute</span></span>|<span data-ttu-id="a62d4-117">描述</span><span class="sxs-lookup"><span data-stu-id="a62d4-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a62d4-118">NAME</span><span class="sxs-lookup"><span data-stu-id="a62d4-118">name</span></span>|<span data-ttu-id="a62d4-119">一个字符串，指定该参数的名称。</span><span class="sxs-lookup"><span data-stu-id="a62d4-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a62d4-120">子元素</span><span class="sxs-lookup"><span data-stu-id="a62d4-120">Child Elements</span></span>  
 <span data-ttu-id="a62d4-121">无。</span><span class="sxs-lookup"><span data-stu-id="a62d4-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a62d4-122">父元素</span><span class="sxs-lookup"><span data-stu-id="a62d4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="a62d4-123">元素</span><span class="sxs-lookup"><span data-stu-id="a62d4-123">Element</span></span>|<span data-ttu-id="a62d4-124">描述</span><span class="sxs-lookup"><span data-stu-id="a62d4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a62d4-125">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="a62d4-125">\<arguments></span></span>](arguments.md)|<span data-ttu-id="a62d4-126">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="a62d4-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a62d4-127">备注</span><span class="sxs-lookup"><span data-stu-id="a62d4-127">Remarks</span></span>  
 <span data-ttu-id="a62d4-128">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="a62d4-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="a62d4-129">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="a62d4-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="a62d4-130">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="a62d4-130">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="a62d4-131">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="a62d4-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="a62d4-132">变量和参数只能通过 ActivityStateRecord 提取, 因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="a62d4-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a62d4-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="a62d4-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a62d4-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="a62d4-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a62d4-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a62d4-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
