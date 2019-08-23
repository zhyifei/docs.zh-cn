---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: dc04405204be7c5484d47b4a3767f846b11abf9f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945506"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="c5bbc-101">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c5bbc-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="c5bbc-102">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="c5bbc-103">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="c5bbc-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="c5bbc-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="c5bbc-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c5bbc-105">\<system.serviceModel></span></span>  
<span data-ttu-id="c5bbc-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="c5bbc-106">\<tracking></span></span>  
<span data-ttu-id="c5bbc-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c5bbc-107">\<trackingProfile></span></span>  
<span data-ttu-id="c5bbc-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="c5bbc-108">\<workflow></span></span>  
<span data-ttu-id="c5bbc-109">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="c5bbc-109">\<activityScheduledQueries></span></span>  
<span data-ttu-id="c5bbc-110">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c5bbc-110">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bbc-111">语法</span><span class="sxs-lookup"><span data-stu-id="c5bbc-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5bbc-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c5bbc-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c5bbc-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5bbc-114">特性</span><span class="sxs-lookup"><span data-stu-id="c5bbc-114">Attributes</span></span>  
  
|<span data-ttu-id="c5bbc-115">特性</span><span class="sxs-lookup"><span data-stu-id="c5bbc-115">Attribute</span></span>|<span data-ttu-id="c5bbc-116">描述</span><span class="sxs-lookup"><span data-stu-id="c5bbc-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5bbc-117">activityName</span><span class="sxs-lookup"><span data-stu-id="c5bbc-117">activityName</span></span>|<span data-ttu-id="c5bbc-118">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="c5bbc-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="c5bbc-119">childActivityName</span></span>|<span data-ttu-id="c5bbc-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5bbc-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c5bbc-121">Child Elements</span></span>  
 <span data-ttu-id="c5bbc-122">无。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5bbc-123">父元素</span><span class="sxs-lookup"><span data-stu-id="c5bbc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="c5bbc-124">元素</span><span class="sxs-lookup"><span data-stu-id="c5bbc-124">Element</span></span>|<span data-ttu-id="c5bbc-125">描述</span><span class="sxs-lookup"><span data-stu-id="c5bbc-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5bbc-126">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="c5bbc-126">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="c5bbc-127">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="c5bbc-127">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c5bbc-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5bbc-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c5bbc-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c5bbc-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c5bbc-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c5bbc-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
