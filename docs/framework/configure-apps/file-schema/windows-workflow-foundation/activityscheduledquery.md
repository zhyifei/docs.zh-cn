---
title: <activityScheduledQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a8bcd6d4-b389-4daf-86bf-1ade85fec114
ms.openlocfilehash: 09cbc43ae4db82dc80e6985131f8d6cc0c24b2ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152406"
---
# <a name="activityscheduledquery"></a><span data-ttu-id="9b1ff-101">\<活动计划查询></span><span class="sxs-lookup"><span data-stu-id="9b1ff-101">\<activityScheduledQuery></span></span>
<span data-ttu-id="9b1ff-102">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="9b1ff-103">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="9b1ff-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="9b1ff-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b1ff-106">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9b1ff-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9b1ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪配置文件>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="9b1ff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="9b1ff-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<活动 计划查询>**](activityscheduledqueries.md)</span><span class="sxs-lookup"><span data-stu-id="9b1ff-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries.md)</span></span>\
<span data-ttu-id="9b1ff-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<活动计划查询>**</span><span class="sxs-lookup"><span data-stu-id="9b1ff-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b1ff-112">语法</span><span class="sxs-lookup"><span data-stu-id="9b1ff-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b1ff-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b1ff-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9b1ff-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b1ff-115">属性</span><span class="sxs-lookup"><span data-stu-id="9b1ff-115">Attributes</span></span>  
  
|<span data-ttu-id="9b1ff-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="9b1ff-116">Attribute</span></span>|<span data-ttu-id="9b1ff-117">说明</span><span class="sxs-lookup"><span data-stu-id="9b1ff-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b1ff-118">activityName</span><span class="sxs-lookup"><span data-stu-id="9b1ff-118">activityName</span></span>|<span data-ttu-id="9b1ff-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="9b1ff-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="9b1ff-120">childActivityName</span></span>|<span data-ttu-id="9b1ff-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b1ff-122">子元素</span><span class="sxs-lookup"><span data-stu-id="9b1ff-122">Child Elements</span></span>  
 <span data-ttu-id="9b1ff-123">无。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b1ff-124">父元素</span><span class="sxs-lookup"><span data-stu-id="9b1ff-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9b1ff-125">元素</span><span class="sxs-lookup"><span data-stu-id="9b1ff-125">Element</span></span>|<span data-ttu-id="9b1ff-126">说明</span><span class="sxs-lookup"><span data-stu-id="9b1ff-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b1ff-127">\<活动计划查询></span><span class="sxs-lookup"><span data-stu-id="9b1ff-127">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="9b1ff-128">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="9b1ff-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b1ff-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b1ff-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9b1ff-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9b1ff-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9b1ff-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9b1ff-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
