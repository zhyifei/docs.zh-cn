---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 695fccf88ac0d8a672e710ccc632ea58dd2fc693
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398771"
---
# <a name="customtrackingquery"></a><span data-ttu-id="68533-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="68533-101">\<customTrackingQuery></span></span>
<span data-ttu-id="68533-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="68533-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="68533-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="68533-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="68533-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="68533-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="68533-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="68533-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="68533-106">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="68533-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="68533-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="68533-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="68533-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="68533-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="68533-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="68533-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="68533-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<q >** ](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="68533-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="68533-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQuery >**</span><span class="sxs-lookup"><span data-stu-id="68533-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68533-112">语法</span><span class="sxs-lookup"><span data-stu-id="68533-112">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
 </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68533-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="68533-113">Attributes and Elements</span></span>  
 <span data-ttu-id="68533-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="68533-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68533-115">特性</span><span class="sxs-lookup"><span data-stu-id="68533-115">Attributes</span></span>  
  
|<span data-ttu-id="68533-116">特性</span><span class="sxs-lookup"><span data-stu-id="68533-116">Attribute</span></span>|<span data-ttu-id="68533-117">描述</span><span class="sxs-lookup"><span data-stu-id="68533-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="68533-118">activityName</span><span class="sxs-lookup"><span data-stu-id="68533-118">activityName</span></span>|<span data-ttu-id="68533-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="68533-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="68533-120">NAME</span><span class="sxs-lookup"><span data-stu-id="68533-120">name</span></span>|<span data-ttu-id="68533-121">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="68533-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68533-122">子元素</span><span class="sxs-lookup"><span data-stu-id="68533-122">Child Elements</span></span>  
 <span data-ttu-id="68533-123">无。</span><span class="sxs-lookup"><span data-stu-id="68533-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68533-124">父元素</span><span class="sxs-lookup"><span data-stu-id="68533-124">Parent Elements</span></span>  
  
|<span data-ttu-id="68533-125">元素</span><span class="sxs-lookup"><span data-stu-id="68533-125">Element</span></span>|<span data-ttu-id="68533-126">描述</span><span class="sxs-lookup"><span data-stu-id="68533-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68533-127">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="68533-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="68533-128">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="68533-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="68533-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="68533-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="68533-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="68533-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="68533-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="68533-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
