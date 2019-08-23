---
title: <activityScheduledQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 7787ada68210ff832ff3fd1ec93c9d346e4d2eaa
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926931"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="4f663-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="4f663-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="4f663-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="4f663-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="4f663-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="4f663-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="4f663-105">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4f663-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4f663-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f663-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4f663-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="4f663-107">\<tracking></span></span>  
<span data-ttu-id="4f663-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="4f663-108">\<profiles></span></span>  
<span data-ttu-id="4f663-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4f663-109">\<trackingProfile></span></span>  
<span data-ttu-id="4f663-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="4f663-110">\<workflow></span></span>  
<span data-ttu-id="4f663-111">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="4f663-111">\<activityScheduledQueries></span></span>  
<span data-ttu-id="4f663-112">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="4f663-112">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f663-113">语法</span><span class="sxs-lookup"><span data-stu-id="4f663-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f663-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4f663-114">Attributes and elements</span></span>  

<span data-ttu-id="4f663-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4f663-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f663-116">特性</span><span class="sxs-lookup"><span data-stu-id="4f663-116">Attributes</span></span>  
  
|<span data-ttu-id="4f663-117">特性</span><span class="sxs-lookup"><span data-stu-id="4f663-117">Attribute</span></span>|<span data-ttu-id="4f663-118">描述</span><span class="sxs-lookup"><span data-stu-id="4f663-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="4f663-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="4f663-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="4f663-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="4f663-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f663-121">子元素</span><span class="sxs-lookup"><span data-stu-id="4f663-121">Child elements</span></span>

<span data-ttu-id="4f663-122">无。</span><span class="sxs-lookup"><span data-stu-id="4f663-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="4f663-123">父元素</span><span class="sxs-lookup"><span data-stu-id="4f663-123">Parent elements</span></span>  
  
|<span data-ttu-id="4f663-124">元素</span><span class="sxs-lookup"><span data-stu-id="4f663-124">Element</span></span>|<span data-ttu-id="4f663-125">描述</span><span class="sxs-lookup"><span data-stu-id="4f663-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f663-126">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="4f663-126">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="4f663-127">查询的集合, 这些查询用于跟踪计划的父活动执行的活动。</span><span class="sxs-lookup"><span data-stu-id="4f663-127">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f663-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f663-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="4f663-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="4f663-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4f663-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4f663-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
