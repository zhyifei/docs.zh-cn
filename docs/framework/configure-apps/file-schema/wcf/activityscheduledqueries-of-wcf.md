---
title: <activityScheduledQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: e351329f-9676-4f11-9b19-f4bac82f36fc
ms.openlocfilehash: c2281a9027aabfc5255ef7b09176f60d1725b522
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850494"
---
# <a name="activityscheduledqueries-of-wcf"></a><span data-ttu-id="02813-102">\<WCF 的 activityScheduledQueries ></span><span class="sxs-lookup"><span data-stu-id="02813-102">\<activityScheduledQueries> of WCF</span></span>
<span data-ttu-id="02813-103">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="02813-103">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="02813-104">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="02813-104">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
<span data-ttu-id="02813-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="02813-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="02813-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="02813-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="02813-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="02813-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="02813-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="02813-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="02813-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="02813-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="02813-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="02813-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="02813-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="02813-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="02813-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityScheduledQueries >**</span><span class="sxs-lookup"><span data-stu-id="02813-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02813-113">语法</span><span class="sxs-lookup"><span data-stu-id="02813-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02813-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02813-114">Attributes and elements</span></span>  

<span data-ttu-id="02813-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02813-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02813-116">特性</span><span class="sxs-lookup"><span data-stu-id="02813-116">Attributes</span></span>  

<span data-ttu-id="02813-117">无。</span><span class="sxs-lookup"><span data-stu-id="02813-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02813-118">子元素</span><span class="sxs-lookup"><span data-stu-id="02813-118">Child elements</span></span>  
  
|<span data-ttu-id="02813-119">元素</span><span class="sxs-lookup"><span data-stu-id="02813-119">Element</span></span>|<span data-ttu-id="02813-120">描述</span><span class="sxs-lookup"><span data-stu-id="02813-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02813-121">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="02813-121">\<activityScheduledQuery></span></span>](activityscheduledquery-of-wcf.md)|<span data-ttu-id="02813-122">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="02813-122">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02813-123">父元素</span><span class="sxs-lookup"><span data-stu-id="02813-123">Parent elements</span></span>  
  
|<span data-ttu-id="02813-124">元素</span><span class="sxs-lookup"><span data-stu-id="02813-124">Element</span></span>|<span data-ttu-id="02813-125">描述</span><span class="sxs-lookup"><span data-stu-id="02813-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02813-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="02813-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="02813-127">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="02813-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02813-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="02813-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityScheduledQuery>
- [<span data-ttu-id="02813-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="02813-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="02813-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="02813-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
