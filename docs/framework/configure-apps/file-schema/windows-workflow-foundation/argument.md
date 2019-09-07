---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: ed08f5533cd6b3839775d061452cb17110cc627e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398906"
---
# <a name="argument"></a><span data-ttu-id="5ccb5-101">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="5ccb5-101">\<argument></span></span>
<span data-ttu-id="5ccb5-102">一个配置元素，表示与某一活动状态查询关联的参数。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="5ccb5-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="5ccb5-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5ccb5-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="5ccb5-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="5ccb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="5ccb5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="5ccb5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Activitystatequeries&gt >** ](activitystatequeries.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries.md)</span></span>\
<span data-ttu-id="5ccb5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityStateQuery >** ](activitystatequery.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQuery>**](activitystatequery.md)</span></span>\
<span data-ttu-id="5ccb5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<参数 >** ](arguments.md)</span><span class="sxs-lookup"><span data-stu-id="5ccb5-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<arguments>**](arguments.md)</span></span>\
<span data-ttu-id="5ccb5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<参数 >**</span><span class="sxs-lookup"><span data-stu-id="5ccb5-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<argument>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ccb5-113">语法</span><span class="sxs-lookup"><span data-stu-id="5ccb5-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ccb5-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5ccb5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="5ccb5-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ccb5-116">特性</span><span class="sxs-lookup"><span data-stu-id="5ccb5-116">Attributes</span></span>  
  
|<span data-ttu-id="5ccb5-117">特性</span><span class="sxs-lookup"><span data-stu-id="5ccb5-117">Attribute</span></span>|<span data-ttu-id="5ccb5-118">描述</span><span class="sxs-lookup"><span data-stu-id="5ccb5-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ccb5-119">NAME</span><span class="sxs-lookup"><span data-stu-id="5ccb5-119">name</span></span>|<span data-ttu-id="5ccb5-120">一个字符串，指定该参数的名称。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-120">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ccb5-121">子元素</span><span class="sxs-lookup"><span data-stu-id="5ccb5-121">Child Elements</span></span>  
 <span data-ttu-id="5ccb5-122">无。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ccb5-123">父元素</span><span class="sxs-lookup"><span data-stu-id="5ccb5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5ccb5-124">元素</span><span class="sxs-lookup"><span data-stu-id="5ccb5-124">Element</span></span>|<span data-ttu-id="5ccb5-125">描述</span><span class="sxs-lookup"><span data-stu-id="5ccb5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ccb5-126">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="5ccb5-126">\<arguments></span></span>](arguments.md)|<span data-ttu-id="5ccb5-127">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-127">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ccb5-128">备注</span><span class="sxs-lookup"><span data-stu-id="5ccb5-128">Remarks</span></span>  
 <span data-ttu-id="5ccb5-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="5ccb5-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="5ccb5-131">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="5ccb5-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="5ccb5-133">变量和参数只能通过 ActivityStateRecord 提取，因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="5ccb5-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5ccb5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ccb5-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5ccb5-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="5ccb5-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5ccb5-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="5ccb5-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
