---
title: '&lt;bookmarkResumptionQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: b0ce29213f1f281e8581b90dda17aba1bdc29072
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltbookmarkresumptionqueriesgt"></a><span data-ttu-id="79949-102">&lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="79949-102">&lt;bookmarkResumptionQueries&gt;</span></span>
<span data-ttu-id="79949-103">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="79949-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="79949-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="79949-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="79949-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="79949-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="79949-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="79949-106">\<system.serviceModel></span></span>  
<span data-ttu-id="79949-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="79949-107">\<tracking></span></span>  
<span data-ttu-id="79949-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="79949-108">\<trackingProfile></span></span>  
<span data-ttu-id="79949-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="79949-109">\<workflow></span></span>  
<span data-ttu-id="79949-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="79949-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="79949-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="79949-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79949-112">语法</span><span class="sxs-lookup"><span data-stu-id="79949-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79949-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79949-113">Attributes and Elements</span></span>  
 <span data-ttu-id="79949-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79949-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79949-115">特性</span><span class="sxs-lookup"><span data-stu-id="79949-115">Attributes</span></span>  
 <span data-ttu-id="79949-116">无。</span><span class="sxs-lookup"><span data-stu-id="79949-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79949-117">子元素</span><span class="sxs-lookup"><span data-stu-id="79949-117">Child Elements</span></span>  
  
|<span data-ttu-id="79949-118">元素</span><span class="sxs-lookup"><span data-stu-id="79949-118">Element</span></span>|<span data-ttu-id="79949-119">描述</span><span class="sxs-lookup"><span data-stu-id="79949-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79949-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="79949-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="79949-121">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="79949-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="79949-122">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="79949-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79949-123">父元素</span><span class="sxs-lookup"><span data-stu-id="79949-123">Parent Elements</span></span>  
  
|<span data-ttu-id="79949-124">元素</span><span class="sxs-lookup"><span data-stu-id="79949-124">Element</span></span>|<span data-ttu-id="79949-125">描述</span><span class="sxs-lookup"><span data-stu-id="79949-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79949-126">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="79949-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="79949-127">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="79949-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79949-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="79949-128">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="79949-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="79949-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="79949-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="79949-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
