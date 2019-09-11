---
title: <activityScheduledQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
ms.openlocfilehash: b173964cf5d691f4b9300bca69ca4a1fe1ea7e11
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850474"
---
# <a name="activityscheduledquery-of-wcf"></a><span data-ttu-id="44aa6-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="44aa6-102">\<activityScheduledQuery> of WCF</span></span>

<span data-ttu-id="44aa6-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="44aa6-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="44aa6-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="44aa6-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="44aa6-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="44aa6-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="44aa6-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="44aa6-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="44aa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="44aa6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="44aa6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="44aa6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="44aa6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<activityScheduledQueries >** ](activityscheduledqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="44aa6-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityScheduledQueries>**](activityscheduledqueries-of-wcf.md)</span></span>\
<span data-ttu-id="44aa6-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="44aa6-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44aa6-114">语法</span><span class="sxs-lookup"><span data-stu-id="44aa6-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44aa6-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="44aa6-115">Attributes and elements</span></span>  

<span data-ttu-id="44aa6-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="44aa6-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44aa6-117">特性</span><span class="sxs-lookup"><span data-stu-id="44aa6-117">Attributes</span></span>  
  
|<span data-ttu-id="44aa6-118">特性</span><span class="sxs-lookup"><span data-stu-id="44aa6-118">Attribute</span></span>|<span data-ttu-id="44aa6-119">描述</span><span class="sxs-lookup"><span data-stu-id="44aa6-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="44aa6-120">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="44aa6-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="44aa6-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="44aa6-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44aa6-122">子元素</span><span class="sxs-lookup"><span data-stu-id="44aa6-122">Child elements</span></span>

<span data-ttu-id="44aa6-123">无。</span><span class="sxs-lookup"><span data-stu-id="44aa6-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="44aa6-124">父元素</span><span class="sxs-lookup"><span data-stu-id="44aa6-124">Parent elements</span></span>  
  
|<span data-ttu-id="44aa6-125">元素</span><span class="sxs-lookup"><span data-stu-id="44aa6-125">Element</span></span>|<span data-ttu-id="44aa6-126">描述</span><span class="sxs-lookup"><span data-stu-id="44aa6-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="44aa6-127">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="44aa6-127">\<activityScheduledQueries></span></span>](activityscheduledqueries-of-wcf.md)|<span data-ttu-id="44aa6-128">查询的集合，这些查询用于跟踪计划的父活动执行的活动。</span><span class="sxs-lookup"><span data-stu-id="44aa6-128">A collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44aa6-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="44aa6-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="44aa6-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="44aa6-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="44aa6-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="44aa6-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
