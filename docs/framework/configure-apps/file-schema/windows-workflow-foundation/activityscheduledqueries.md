---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: 7217fb886cc96e1ad19f96e2c6542277cfc7979e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790424"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="1c266-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="1c266-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="1c266-102">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="1c266-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="1c266-103">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="1c266-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="1c266-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1c266-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1c266-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1c266-105">\<system.serviceModel></span></span>  
<span data-ttu-id="1c266-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="1c266-106">\<tracking></span></span>  
<span data-ttu-id="1c266-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1c266-107">\<trackingProfile></span></span>  
<span data-ttu-id="1c266-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1c266-108">\<workflow></span></span>  
<span data-ttu-id="1c266-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="1c266-109">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c266-110">语法</span><span class="sxs-lookup"><span data-stu-id="1c266-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1c266-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1c266-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1c266-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1c266-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1c266-113">特性</span><span class="sxs-lookup"><span data-stu-id="1c266-113">Attributes</span></span>  
 <span data-ttu-id="1c266-114">无。</span><span class="sxs-lookup"><span data-stu-id="1c266-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1c266-115">子元素</span><span class="sxs-lookup"><span data-stu-id="1c266-115">Child Elements</span></span>  
  
|<span data-ttu-id="1c266-116">元素</span><span class="sxs-lookup"><span data-stu-id="1c266-116">Element</span></span>|<span data-ttu-id="1c266-117">描述</span><span class="sxs-lookup"><span data-stu-id="1c266-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c266-118">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="1c266-118">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="1c266-119">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="1c266-119">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1c266-120">父元素</span><span class="sxs-lookup"><span data-stu-id="1c266-120">Parent Elements</span></span>  
  
|<span data-ttu-id="1c266-121">元素</span><span class="sxs-lookup"><span data-stu-id="1c266-121">Element</span></span>|<span data-ttu-id="1c266-122">描述</span><span class="sxs-lookup"><span data-stu-id="1c266-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1c266-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1c266-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1c266-124">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="1c266-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c266-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c266-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1c266-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1c266-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1c266-127">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1c266-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
