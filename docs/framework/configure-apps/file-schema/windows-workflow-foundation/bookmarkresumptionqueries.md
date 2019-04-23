---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 186990577ec4eedc7cae3710c455816c3162fc94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109404"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="210f4-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="210f4-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="210f4-102">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="210f4-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="210f4-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="210f4-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="210f4-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="210f4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="210f4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="210f4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="210f4-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="210f4-106">\<tracking></span></span>  
<span data-ttu-id="210f4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="210f4-107">\<trackingProfile></span></span>  
<span data-ttu-id="210f4-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="210f4-108">\<workflow></span></span>  
<span data-ttu-id="210f4-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="210f4-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="210f4-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="210f4-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="210f4-111">语法</span><span class="sxs-lookup"><span data-stu-id="210f4-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="210f4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="210f4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="210f4-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="210f4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="210f4-114">特性</span><span class="sxs-lookup"><span data-stu-id="210f4-114">Attributes</span></span>  
 <span data-ttu-id="210f4-115">无。</span><span class="sxs-lookup"><span data-stu-id="210f4-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="210f4-116">子元素</span><span class="sxs-lookup"><span data-stu-id="210f4-116">Child Elements</span></span>  
  
|<span data-ttu-id="210f4-117">元素</span><span class="sxs-lookup"><span data-stu-id="210f4-117">Element</span></span>|<span data-ttu-id="210f4-118">描述</span><span class="sxs-lookup"><span data-stu-id="210f4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="210f4-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="210f4-119">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="210f4-120">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="210f4-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="210f4-121">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="210f4-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="210f4-122">父元素</span><span class="sxs-lookup"><span data-stu-id="210f4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="210f4-123">元素</span><span class="sxs-lookup"><span data-stu-id="210f4-123">Element</span></span>|<span data-ttu-id="210f4-124">描述</span><span class="sxs-lookup"><span data-stu-id="210f4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="210f4-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="210f4-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="210f4-126">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="210f4-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="210f4-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="210f4-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="210f4-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="210f4-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="210f4-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="210f4-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
