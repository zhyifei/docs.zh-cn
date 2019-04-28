---
title: <activityScheduledQueries> WCF 的
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: 1c9c292080016d7a2d0014ed07be371c0e247621
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701120"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="2cfdf-102">\<activityScheduledQueries > 的 WCF</span><span class="sxs-lookup"><span data-stu-id="2cfdf-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="2cfdf-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="2cfdf-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="2cfdf-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="2cfdf-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="2cfdf-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2cfdf-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2cfdf-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2cfdf-106">\<system.serviceModel></span></span>  
<span data-ttu-id="2cfdf-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2cfdf-107">\<tracking></span></span>  
<span data-ttu-id="2cfdf-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="2cfdf-108">\<profiles></span></span>  
<span data-ttu-id="2cfdf-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2cfdf-109">\<trackingProfile></span></span>  
<span data-ttu-id="2cfdf-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2cfdf-110">\<workflow></span></span>  
<span data-ttu-id="2cfdf-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="2cfdf-111">\<activityScheduledQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cfdf-112">语法</span><span class="sxs-lookup"><span data-stu-id="2cfdf-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityScheduledQueries>
          <activityScheduledQuery activityName="String"
                                  childActivityName="String" />
        </activityScheduledQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cfdf-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2cfdf-113">Attributes and elements</span></span>  

<span data-ttu-id="2cfdf-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2cfdf-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cfdf-115">特性</span><span class="sxs-lookup"><span data-stu-id="2cfdf-115">Attributes</span></span>  

<span data-ttu-id="2cfdf-116">无。</span><span class="sxs-lookup"><span data-stu-id="2cfdf-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2cfdf-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2cfdf-117">Child elements</span></span>  
  
|<span data-ttu-id="2cfdf-118">元素</span><span class="sxs-lookup"><span data-stu-id="2cfdf-118">Element</span></span>|<span data-ttu-id="2cfdf-119">描述</span><span class="sxs-lookup"><span data-stu-id="2cfdf-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cfdf-120">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="2cfdf-120">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="2cfdf-121">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="2cfdf-121">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2cfdf-122">父元素</span><span class="sxs-lookup"><span data-stu-id="2cfdf-122">Parent elements</span></span>  
  
|<span data-ttu-id="2cfdf-123">元素</span><span class="sxs-lookup"><span data-stu-id="2cfdf-123">Element</span></span>|<span data-ttu-id="2cfdf-124">描述</span><span class="sxs-lookup"><span data-stu-id="2cfdf-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cfdf-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2cfdf-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="2cfdf-126">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="2cfdf-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2cfdf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="2cfdf-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="2cfdf-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2cfdf-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2cfdf-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="2cfdf-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
