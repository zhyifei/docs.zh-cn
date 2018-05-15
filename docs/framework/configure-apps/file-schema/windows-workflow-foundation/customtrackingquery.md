---
title: '&lt;customTrackingQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 7ddf19ed75d50f3cd5f20de8b0e2dfcdd5ea82b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingquerygt"></a><span data-ttu-id="599c9-102">&lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="599c9-102">&lt;customTrackingQuery&gt;</span></span>
<span data-ttu-id="599c9-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="599c9-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="599c9-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="599c9-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="599c9-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="599c9-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="599c9-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="599c9-106">\<system.serviceModel></span></span>  
<span data-ttu-id="599c9-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="599c9-107">\<tracking></span></span>  
<span data-ttu-id="599c9-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="599c9-108">\<trackingProfile></span></span>  
<span data-ttu-id="599c9-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="599c9-109">\<workflow></span></span>  
<span data-ttu-id="599c9-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="599c9-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="599c9-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="599c9-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="599c9-112">语法</span><span class="sxs-lookup"><span data-stu-id="599c9-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="599c9-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="599c9-113">Attributes and Elements</span></span>  
 <span data-ttu-id="599c9-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="599c9-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="599c9-115">特性</span><span class="sxs-lookup"><span data-stu-id="599c9-115">Attributes</span></span>  
  
|<span data-ttu-id="599c9-116">特性</span><span class="sxs-lookup"><span data-stu-id="599c9-116">Attribute</span></span>|<span data-ttu-id="599c9-117">描述</span><span class="sxs-lookup"><span data-stu-id="599c9-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="599c9-118">activityName</span><span class="sxs-lookup"><span data-stu-id="599c9-118">activityName</span></span>|<span data-ttu-id="599c9-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="599c9-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="599c9-120">name</span><span class="sxs-lookup"><span data-stu-id="599c9-120">name</span></span>|<span data-ttu-id="599c9-121">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="599c9-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="599c9-122">子元素</span><span class="sxs-lookup"><span data-stu-id="599c9-122">Child Elements</span></span>  
 <span data-ttu-id="599c9-123">无。</span><span class="sxs-lookup"><span data-stu-id="599c9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="599c9-124">父元素</span><span class="sxs-lookup"><span data-stu-id="599c9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="599c9-125">元素</span><span class="sxs-lookup"><span data-stu-id="599c9-125">Element</span></span>|<span data-ttu-id="599c9-126">描述</span><span class="sxs-lookup"><span data-stu-id="599c9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="599c9-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="599c9-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="599c9-128">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="599c9-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="599c9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="599c9-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>         
 [<span data-ttu-id="599c9-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="599c9-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="599c9-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="599c9-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
