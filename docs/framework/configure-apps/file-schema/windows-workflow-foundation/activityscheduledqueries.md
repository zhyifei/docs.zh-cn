---
title: '&lt;activityScheduledQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 6192fea9a520a3f453593e5efac964a5d32a492f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756288"
---
# <a name="ltactivityscheduledqueriesgt"></a><span data-ttu-id="a5696-102">&lt;activityScheduledQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="a5696-102">&lt;activityScheduledQueries&gt;</span></span>
<span data-ttu-id="a5696-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="a5696-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="a5696-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="a5696-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="a5696-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a5696-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a5696-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a5696-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a5696-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="a5696-107">\<tracking></span></span>  
<span data-ttu-id="a5696-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a5696-108">\<trackingProfile></span></span>  
<span data-ttu-id="a5696-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="a5696-109">\<workflow></span></span>  
<span data-ttu-id="a5696-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="a5696-110">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5696-111">语法</span><span class="sxs-lookup"><span data-stu-id="a5696-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5696-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a5696-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a5696-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a5696-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5696-114">特性</span><span class="sxs-lookup"><span data-stu-id="a5696-114">Attributes</span></span>  
 <span data-ttu-id="a5696-115">无。</span><span class="sxs-lookup"><span data-stu-id="a5696-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a5696-116">子元素</span><span class="sxs-lookup"><span data-stu-id="a5696-116">Child Elements</span></span>  
  
|<span data-ttu-id="a5696-117">元素</span><span class="sxs-lookup"><span data-stu-id="a5696-117">Element</span></span>|<span data-ttu-id="a5696-118">描述</span><span class="sxs-lookup"><span data-stu-id="a5696-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5696-119">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="a5696-119">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="a5696-120">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="a5696-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5696-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a5696-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a5696-122">元素</span><span class="sxs-lookup"><span data-stu-id="a5696-122">Element</span></span>|<span data-ttu-id="a5696-123">描述</span><span class="sxs-lookup"><span data-stu-id="a5696-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5696-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="a5696-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a5696-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="a5696-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a5696-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5696-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a5696-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="a5696-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a5696-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a5696-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
