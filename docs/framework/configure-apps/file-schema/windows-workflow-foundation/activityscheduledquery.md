---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: d49c6d933a09dce5d657746358f1a5f716ab639b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59143359"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="2b765-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="2b765-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="2b765-102">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="2b765-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="2b765-103">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="2b765-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="2b765-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2b765-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2b765-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2b765-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2b765-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="2b765-106">\<tracking></span></span>  
<span data-ttu-id="2b765-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2b765-107">\<trackingProfile></span></span>  
<span data-ttu-id="2b765-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="2b765-108">\<workflow></span></span>  
<span data-ttu-id="2b765-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="2b765-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="2b765-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="2b765-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b765-111">语法</span><span class="sxs-lookup"><span data-stu-id="2b765-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b765-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b765-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2b765-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2b765-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b765-114">特性</span><span class="sxs-lookup"><span data-stu-id="2b765-114">Attributes</span></span>  
  
|<span data-ttu-id="2b765-115">特性</span><span class="sxs-lookup"><span data-stu-id="2b765-115">Attribute</span></span>|<span data-ttu-id="2b765-116">描述</span><span class="sxs-lookup"><span data-stu-id="2b765-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b765-117">activityName</span><span class="sxs-lookup"><span data-stu-id="2b765-117">activityName</span></span>|<span data-ttu-id="2b765-118">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="2b765-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="2b765-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="2b765-119">childActivityName</span></span>|<span data-ttu-id="2b765-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="2b765-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b765-121">子元素</span><span class="sxs-lookup"><span data-stu-id="2b765-121">Child Elements</span></span>  
 <span data-ttu-id="2b765-122">无。</span><span class="sxs-lookup"><span data-stu-id="2b765-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b765-123">父元素</span><span class="sxs-lookup"><span data-stu-id="2b765-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2b765-124">元素</span><span class="sxs-lookup"><span data-stu-id="2b765-124">Element</span></span>|<span data-ttu-id="2b765-125">描述</span><span class="sxs-lookup"><span data-stu-id="2b765-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b765-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="2b765-126">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="2b765-127">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="2b765-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b765-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b765-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2b765-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2b765-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2b765-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="2b765-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
