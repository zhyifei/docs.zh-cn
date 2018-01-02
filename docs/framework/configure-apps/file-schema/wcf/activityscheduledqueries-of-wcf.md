---
title: "WCF 的 &lt;activityScheduledQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5a857a86d45226e3dd3805a900612f55078c0bf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="19ca4-102">WCF 的 &lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="19ca4-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="19ca4-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="19ca4-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="19ca4-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="19ca4-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="19ca4-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="19ca4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="19ca4-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="19ca4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="19ca4-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="19ca4-107">\<tracking></span></span>  
<span data-ttu-id="19ca4-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="19ca4-108">\<trackingProfile></span></span>  
<span data-ttu-id="19ca4-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="19ca4-109">\<workflow></span></span>  
<span data-ttu-id="19ca4-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="19ca4-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ca4-111">语法</span><span class="sxs-lookup"><span data-stu-id="19ca4-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19ca4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="19ca4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="19ca4-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="19ca4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19ca4-114">特性</span><span class="sxs-lookup"><span data-stu-id="19ca4-114">Attributes</span></span>  
 <span data-ttu-id="19ca4-115">无。</span><span class="sxs-lookup"><span data-stu-id="19ca4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="19ca4-116">子元素</span><span class="sxs-lookup"><span data-stu-id="19ca4-116">Child Elements</span></span>  
  
|<span data-ttu-id="19ca4-117">元素</span><span class="sxs-lookup"><span data-stu-id="19ca4-117">Element</span></span>|<span data-ttu-id="19ca4-118">描述</span><span class="sxs-lookup"><span data-stu-id="19ca4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19ca4-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="19ca4-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="19ca4-120">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="19ca4-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="19ca4-121">父元素</span><span class="sxs-lookup"><span data-stu-id="19ca4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="19ca4-122">元素</span><span class="sxs-lookup"><span data-stu-id="19ca4-122">Element</span></span>|<span data-ttu-id="19ca4-123">描述</span><span class="sxs-lookup"><span data-stu-id="19ca4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19ca4-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="19ca4-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="19ca4-125">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="19ca4-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19ca4-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="19ca4-126">See Also</span></span>  
 <span data-ttu-id="19ca4-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="19ca4-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection></span></span>     
 <span data-ttu-id="19ca4-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="19ca4-128"><xref:System.Activities.Tracking.ActivityScheduledQuery></span></span>     
 [<span data-ttu-id="19ca4-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="19ca4-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="19ca4-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="19ca4-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
