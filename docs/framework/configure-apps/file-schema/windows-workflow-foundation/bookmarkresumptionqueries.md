---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: f048612673a9b6b69c3cdded6526c76359c444e9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945979"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="863c3-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="863c3-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="863c3-102">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="863c3-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="863c3-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="863c3-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="863c3-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="863c3-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="863c3-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="863c3-105">\<system.serviceModel></span></span>  
<span data-ttu-id="863c3-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="863c3-106">\<tracking></span></span>  
<span data-ttu-id="863c3-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="863c3-107">\<trackingProfile></span></span>  
<span data-ttu-id="863c3-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="863c3-108">\<workflow></span></span>  
<span data-ttu-id="863c3-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="863c3-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="863c3-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="863c3-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="863c3-111">语法</span><span class="sxs-lookup"><span data-stu-id="863c3-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <bookmarkResumptionQueries>
        <bookmarkResumptionQuery name="String" />
      </bookmarkResumptionQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="863c3-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="863c3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="863c3-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="863c3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="863c3-114">特性</span><span class="sxs-lookup"><span data-stu-id="863c3-114">Attributes</span></span>  
 <span data-ttu-id="863c3-115">无。</span><span class="sxs-lookup"><span data-stu-id="863c3-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="863c3-116">子元素</span><span class="sxs-lookup"><span data-stu-id="863c3-116">Child Elements</span></span>  
  
|<span data-ttu-id="863c3-117">元素</span><span class="sxs-lookup"><span data-stu-id="863c3-117">Element</span></span>|<span data-ttu-id="863c3-118">描述</span><span class="sxs-lookup"><span data-stu-id="863c3-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="863c3-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="863c3-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="863c3-120">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="863c3-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="863c3-121">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="863c3-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="863c3-122">父元素</span><span class="sxs-lookup"><span data-stu-id="863c3-122">Parent Elements</span></span>  
  
|<span data-ttu-id="863c3-123">元素</span><span class="sxs-lookup"><span data-stu-id="863c3-123">Element</span></span>|<span data-ttu-id="863c3-124">描述</span><span class="sxs-lookup"><span data-stu-id="863c3-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="863c3-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="863c3-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="863c3-126">一个配置元素, 该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="863c3-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="863c3-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="863c3-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="863c3-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="863c3-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="863c3-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="863c3-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
