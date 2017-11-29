---
title: "WCF 的 &lt;customTrackingQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c88a5d0e15acf67061976826a65faf5bfacb8384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="e76db-102">WCF 的 &lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="e76db-102">&lt;customTrackingQuery&gt; of WCF</span></span>
<span data-ttu-id="e76db-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e76db-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e76db-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="e76db-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e76db-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e76db-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="e76db-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e76db-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e76db-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e76db-107">\<tracking></span></span>  
<span data-ttu-id="e76db-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e76db-108">\<trackingProfile></span></span>  
<span data-ttu-id="e76db-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e76db-109">\<workflow></span></span>  
<span data-ttu-id="e76db-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="e76db-110">\<customTrackingQueries></span></span>  
<span data-ttu-id="e76db-111">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e76db-111">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e76db-112">语法</span><span class="sxs-lookup"><span data-stu-id="e76db-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e76db-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e76db-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e76db-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e76db-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e76db-115">特性</span><span class="sxs-lookup"><span data-stu-id="e76db-115">Attributes</span></span>  
  
|<span data-ttu-id="e76db-116">特性</span><span class="sxs-lookup"><span data-stu-id="e76db-116">Attribute</span></span>|<span data-ttu-id="e76db-117">描述</span><span class="sxs-lookup"><span data-stu-id="e76db-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e76db-118">activityName</span><span class="sxs-lookup"><span data-stu-id="e76db-118">activityName</span></span>|<span data-ttu-id="e76db-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="e76db-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="e76db-120">name</span><span class="sxs-lookup"><span data-stu-id="e76db-120">name</span></span>|<span data-ttu-id="e76db-121">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="e76db-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e76db-122">子元素</span><span class="sxs-lookup"><span data-stu-id="e76db-122">Child Elements</span></span>  
 <span data-ttu-id="e76db-123">无。</span><span class="sxs-lookup"><span data-stu-id="e76db-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e76db-124">父元素</span><span class="sxs-lookup"><span data-stu-id="e76db-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e76db-125">元素</span><span class="sxs-lookup"><span data-stu-id="e76db-125">Element</span></span>|<span data-ttu-id="e76db-126">描述</span><span class="sxs-lookup"><span data-stu-id="e76db-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e76db-127">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e76db-127">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="e76db-128">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e76db-128">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e76db-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e76db-129">See Also</span></span>  
 <span data-ttu-id="e76db-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e76db-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>      
 <span data-ttu-id="e76db-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e76db-131"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="e76db-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e76db-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e76db-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e76db-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
