---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: a02d71811709b2c285ab7081b89ee3082ec5b43d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152204"
---
# <a name="customtrackingquery"></a><span data-ttu-id="9b0d6-101">\<自定义跟踪查询></span><span class="sxs-lookup"><span data-stu-id="9b0d6-101">\<customTrackingQuery></span></span>
<span data-ttu-id="9b0d6-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9b0d6-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="9b0d6-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9b0d6-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b0d6-106">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9b0d6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9b0d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪配置文件>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="9b0d6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="9b0d6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<自定义跟踪查询>**](customtrackingqueries.md)</span><span class="sxs-lookup"><span data-stu-id="9b0d6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries.md)</span></span>\
<span data-ttu-id="9b0d6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<自定义跟踪查询>**</span><span class="sxs-lookup"><span data-stu-id="9b0d6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b0d6-112">语法</span><span class="sxs-lookup"><span data-stu-id="9b0d6-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b0d6-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b0d6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9b0d6-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b0d6-115">属性</span><span class="sxs-lookup"><span data-stu-id="9b0d6-115">Attributes</span></span>  
  
|<span data-ttu-id="9b0d6-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b0d6-116">Attribute</span></span>|<span data-ttu-id="9b0d6-117">说明</span><span class="sxs-lookup"><span data-stu-id="9b0d6-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b0d6-118">activityName</span><span class="sxs-lookup"><span data-stu-id="9b0d6-118">activityName</span></span>|<span data-ttu-id="9b0d6-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="9b0d6-120">name</span><span class="sxs-lookup"><span data-stu-id="9b0d6-120">name</span></span>|<span data-ttu-id="9b0d6-121">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b0d6-122">子元素</span><span class="sxs-lookup"><span data-stu-id="9b0d6-122">Child Elements</span></span>  
 <span data-ttu-id="9b0d6-123">无。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b0d6-124">父元素</span><span class="sxs-lookup"><span data-stu-id="9b0d6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9b0d6-125">元素</span><span class="sxs-lookup"><span data-stu-id="9b0d6-125">Element</span></span>|<span data-ttu-id="9b0d6-126">说明</span><span class="sxs-lookup"><span data-stu-id="9b0d6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b0d6-127">\<自定义跟踪查询></span><span class="sxs-lookup"><span data-stu-id="9b0d6-127">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="9b0d6-128">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="9b0d6-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b0d6-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b0d6-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9b0d6-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9b0d6-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9b0d6-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9b0d6-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
