---
title: WCF 的 &lt;activityScheduledQuery&gt;
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: 9a53d72316dad0178f24e05656a4fb4531b88aec
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087760"
---
# <a name="ltactivityscheduledquerygt-of-wcf"></a><span data-ttu-id="7c326-102">WCF 的 &lt;activityScheduledQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="7c326-102">&lt;activityScheduledQuery&gt; of WCF</span></span>
<span data-ttu-id="7c326-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="7c326-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="7c326-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="7c326-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="7c326-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7c326-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="7c326-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7c326-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7c326-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7c326-107">\<tracking></span></span>  
<span data-ttu-id="7c326-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7c326-108">\<trackingProfile></span></span>  
<span data-ttu-id="7c326-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="7c326-109">\<workflow></span></span>  
<span data-ttu-id="7c326-110">\<activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="7c326-110">\<activityScheduledQueries></span></span>  
<span data-ttu-id="7c326-111">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="7c326-111">\<activityScheduledQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c326-112">语法</span><span class="sxs-lookup"><span data-stu-id="7c326-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7c326-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7c326-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7c326-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7c326-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7c326-115">特性</span><span class="sxs-lookup"><span data-stu-id="7c326-115">Attributes</span></span>  
  
|<span data-ttu-id="7c326-116">特性</span><span class="sxs-lookup"><span data-stu-id="7c326-116">Attribute</span></span>|<span data-ttu-id="7c326-117">描述</span><span class="sxs-lookup"><span data-stu-id="7c326-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7c326-118">activityName</span><span class="sxs-lookup"><span data-stu-id="7c326-118">activityName</span></span>|<span data-ttu-id="7c326-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7c326-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="7c326-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="7c326-120">childActivityName</span></span>|<span data-ttu-id="7c326-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7c326-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7c326-122">子元素</span><span class="sxs-lookup"><span data-stu-id="7c326-122">Child Elements</span></span>  
 <span data-ttu-id="7c326-123">无。</span><span class="sxs-lookup"><span data-stu-id="7c326-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7c326-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7c326-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7c326-125">元素</span><span class="sxs-lookup"><span data-stu-id="7c326-125">Element</span></span>|<span data-ttu-id="7c326-126">描述</span><span class="sxs-lookup"><span data-stu-id="7c326-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7c326-127">\<activityScheduledQuery ></span><span class="sxs-lookup"><span data-stu-id="7c326-127">\<activityScheduledQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|<span data-ttu-id="7c326-128">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="7c326-128">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7c326-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c326-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>     
 <xref:System.Activities.Tracking.ActivityScheduledQuery>     
 [<span data-ttu-id="7c326-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7c326-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7c326-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7c326-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
