---
title: '&lt;activityScheduledQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 51db0762c10459d67929867a0fe44908dc7ec750
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledquerygt"></a><span data-ttu-id="7e72d-102">&lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="7e72d-102">&lt;activityScheduledQuery&gt;</span></span>
<span data-ttu-id="7e72d-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="7e72d-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7e72d-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="7e72d-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="7e72d-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7e72d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7e72d-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="7e72d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7e72d-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7e72d-107">\<tracking></span></span>  
<span data-ttu-id="7e72d-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7e72d-108">\<trackingProfile></span></span>  
<span data-ttu-id="7e72d-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="7e72d-109">\<workflow></span></span>  
<span data-ttu-id="7e72d-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="7e72d-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="7e72d-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="7e72d-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e72d-112">语法</span><span class="sxs-lookup"><span data-stu-id="7e72d-112">Syntax</span></span>  
  
```xml 
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String"/>
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e72d-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7e72d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7e72d-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7e72d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e72d-115">特性</span><span class="sxs-lookup"><span data-stu-id="7e72d-115">Attributes</span></span>  
  
|<span data-ttu-id="7e72d-116">特性</span><span class="sxs-lookup"><span data-stu-id="7e72d-116">Attribute</span></span>|<span data-ttu-id="7e72d-117">描述</span><span class="sxs-lookup"><span data-stu-id="7e72d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e72d-118">activityName</span><span class="sxs-lookup"><span data-stu-id="7e72d-118">activityName</span></span>|<span data-ttu-id="7e72d-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7e72d-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="7e72d-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="7e72d-120">childActivityName</span></span>|<span data-ttu-id="7e72d-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7e72d-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e72d-122">子元素</span><span class="sxs-lookup"><span data-stu-id="7e72d-122">Child Elements</span></span>  
 <span data-ttu-id="7e72d-123">无。</span><span class="sxs-lookup"><span data-stu-id="7e72d-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e72d-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7e72d-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7e72d-125">元素</span><span class="sxs-lookup"><span data-stu-id="7e72d-125">Element</span></span>|<span data-ttu-id="7e72d-126">描述</span><span class="sxs-lookup"><span data-stu-id="7e72d-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e72d-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="7e72d-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="7e72d-128">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="7e72d-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7e72d-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e72d-129">See Also</span></span>  
 <span data-ttu-id="7e72d-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7e72d-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="7e72d-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7e72d-131"><xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="7e72d-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7e72d-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7e72d-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7e72d-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
