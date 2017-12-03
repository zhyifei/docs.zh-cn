---
title: "WCF 的 &lt;activityScheduledQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 260b77789df6a03b640895ed158c94bfd1533f9b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="6f1aa-102">WCF 的 &lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6f1aa-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="6f1aa-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="6f1aa-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="6f1aa-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6f1aa-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="6f1aa-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6f1aa-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-107">\<tracking></span></span>  
<span data-ttu-id="6f1aa-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-108">\<trackingProfile></span></span>  
<span data-ttu-id="6f1aa-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-109">\<workflow></span></span>  
<span data-ttu-id="6f1aa-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="6f1aa-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f1aa-112">语法</span><span class="sxs-lookup"><span data-stu-id="6f1aa-112">Syntax</span></span>  
  
```xml
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f1aa-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f1aa-113">Attributes and Elements</span></span>  
 <span data-ttu-id="6f1aa-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f1aa-115">特性</span><span class="sxs-lookup"><span data-stu-id="6f1aa-115">Attributes</span></span>  
  
|<span data-ttu-id="6f1aa-116">特性</span><span class="sxs-lookup"><span data-stu-id="6f1aa-116">Attribute</span></span>|<span data-ttu-id="6f1aa-117">描述</span><span class="sxs-lookup"><span data-stu-id="6f1aa-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f1aa-118">activityName</span><span class="sxs-lookup"><span data-stu-id="6f1aa-118">activityName</span></span>|<span data-ttu-id="6f1aa-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="6f1aa-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="6f1aa-120">childActivityName</span></span>|<span data-ttu-id="6f1aa-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f1aa-122">子元素</span><span class="sxs-lookup"><span data-stu-id="6f1aa-122">Child Elements</span></span>  
 <span data-ttu-id="6f1aa-123">无。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f1aa-124">父元素</span><span class="sxs-lookup"><span data-stu-id="6f1aa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="6f1aa-125">元素</span><span class="sxs-lookup"><span data-stu-id="6f1aa-125">Element</span></span>|<span data-ttu-id="6f1aa-126">描述</span><span class="sxs-lookup"><span data-stu-id="6f1aa-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f1aa-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="6f1aa-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="6f1aa-128">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="6f1aa-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f1aa-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f1aa-129">See Also</span></span>  
 <span data-ttu-id="6f1aa-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span><span class="sxs-lookup"><span data-stu-id="6f1aa-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement></span></span>     
 <span data-ttu-id="6f1aa-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="6f1aa-131"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="6f1aa-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6f1aa-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6f1aa-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6f1aa-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
