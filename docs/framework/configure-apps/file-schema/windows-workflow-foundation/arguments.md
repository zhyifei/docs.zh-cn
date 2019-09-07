---
title: <arguments>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 0f327196-f468-4be3-b6c4-68ba981a1bd6
ms.openlocfilehash: f06a2188ea3561437c1453d3a1cb23d42d767f53
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398914"
---
# <a name="arguments"></a><span data-ttu-id="13d8c-101">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="13d8c-101">\<arguments></span></span>
<span data-ttu-id="13d8c-102">表示与某一活动状态查询关联的参数的集合。</span><span class="sxs-lookup"><span data-stu-id="13d8c-102">Represents a collection of arguments associated with an activity state query.</span></span>  
  
 <span data-ttu-id="13d8c-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="13d8c-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="13d8c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="13d8c-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="13d8c-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="13d8c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="13d8c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="13d8c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Activitystatequeries&gt >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="13d8c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="13d8c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="13d8c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<参数 >**</span><span class="sxs-lookup"><span data-stu-id="13d8c-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<arguments>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d8c-112">语法</span><span class="sxs-lookup"><span data-stu-id="13d8c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="13d8c-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="13d8c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="13d8c-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="13d8c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="13d8c-115">特性</span><span class="sxs-lookup"><span data-stu-id="13d8c-115">Attributes</span></span>  
 <span data-ttu-id="13d8c-116">无。</span><span class="sxs-lookup"><span data-stu-id="13d8c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="13d8c-117">子元素</span><span class="sxs-lookup"><span data-stu-id="13d8c-117">Child Elements</span></span>  
  
|<span data-ttu-id="13d8c-118">元素</span><span class="sxs-lookup"><span data-stu-id="13d8c-118">Element</span></span>|<span data-ttu-id="13d8c-119">描述</span><span class="sxs-lookup"><span data-stu-id="13d8c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13d8c-120">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="13d8c-120">\<argument></span></span>](argument.md)|<span data-ttu-id="13d8c-121">与活动状态查询相关联的参数。</span><span class="sxs-lookup"><span data-stu-id="13d8c-121">An argument associated with an activity state query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="13d8c-122">父元素</span><span class="sxs-lookup"><span data-stu-id="13d8c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="13d8c-123">元素</span><span class="sxs-lookup"><span data-stu-id="13d8c-123">Element</span></span>|<span data-ttu-id="13d8c-124">描述</span><span class="sxs-lookup"><span data-stu-id="13d8c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="13d8c-125">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="13d8c-125">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="13d8c-126">表示一个配置元素，该元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="13d8c-126">Represents a configuration element that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="13d8c-127">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="13d8c-127">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13d8c-128">备注</span><span class="sxs-lookup"><span data-stu-id="13d8c-128">Remarks</span></span>  
 <span data-ttu-id="13d8c-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="13d8c-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="13d8c-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="13d8c-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="13d8c-131">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="13d8c-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="13d8c-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="13d8c-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="13d8c-133">变量和参数只能通过 ActivityStateRecord 提取，因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="13d8c-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="13d8c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="13d8c-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="13d8c-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="13d8c-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="13d8c-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="13d8c-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
