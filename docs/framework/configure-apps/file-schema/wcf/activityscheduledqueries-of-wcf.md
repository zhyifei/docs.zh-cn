---
title: WCF 的 &lt;activityScheduledQueries&gt;
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 946406e5513a0fee6793071c397f61bf1fe71c65
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltactivityscheduledqueriesgt-of-wcf"></a><span data-ttu-id="99930-102">WCF 的 &lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="99930-102">&lt;activityScheduledQueries&gt; of WCF</span></span>
<span data-ttu-id="99930-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="99930-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="99930-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="99930-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="99930-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="99930-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="99930-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="99930-106">\<system.serviceModel></span></span>  
<span data-ttu-id="99930-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="99930-107">\<tracking></span></span>  
<span data-ttu-id="99930-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="99930-108">\<trackingProfile></span></span>  
<span data-ttu-id="99930-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="99930-109">\<workflow></span></span>  
<span data-ttu-id="99930-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="99930-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99930-111">语法</span><span class="sxs-lookup"><span data-stu-id="99930-111">Syntax</span></span>  
  
```xml  
<tracking>     <trackingProfile name="Name">       <workflow>          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>       </workflow>     </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99930-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="99930-112">Attributes and Elements</span></span>  
 <span data-ttu-id="99930-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="99930-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99930-114">特性</span><span class="sxs-lookup"><span data-stu-id="99930-114">Attributes</span></span>  
 <span data-ttu-id="99930-115">无。</span><span class="sxs-lookup"><span data-stu-id="99930-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="99930-116">子元素</span><span class="sxs-lookup"><span data-stu-id="99930-116">Child Elements</span></span>  
  
|<span data-ttu-id="99930-117">元素</span><span class="sxs-lookup"><span data-stu-id="99930-117">Element</span></span>|<span data-ttu-id="99930-118">描述</span><span class="sxs-lookup"><span data-stu-id="99930-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99930-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="99930-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="99930-120">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="99930-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="99930-121">父元素</span><span class="sxs-lookup"><span data-stu-id="99930-121">Parent Elements</span></span>  
  
|<span data-ttu-id="99930-122">元素</span><span class="sxs-lookup"><span data-stu-id="99930-122">Element</span></span>|<span data-ttu-id="99930-123">描述</span><span class="sxs-lookup"><span data-stu-id="99930-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99930-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="99930-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="99930-125">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="99930-125">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="99930-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="99930-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="99930-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="99930-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="99930-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="99930-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
