---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 88f9639e4ecc3105a0e58d92e443d9582f261970
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756181"
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="560f1-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="560f1-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="560f1-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="560f1-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="560f1-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="560f1-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="560f1-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="560f1-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="560f1-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="560f1-106">\<system.serviceModel></span></span>  
<span data-ttu-id="560f1-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="560f1-107">\<tracking></span></span>  
<span data-ttu-id="560f1-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="560f1-108">\<trackingProfile></span></span>  
<span data-ttu-id="560f1-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="560f1-109">\<workflow></span></span>  
<span data-ttu-id="560f1-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="560f1-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="560f1-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="560f1-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="560f1-112">语法</span><span class="sxs-lookup"><span data-stu-id="560f1-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="560f1-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="560f1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="560f1-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="560f1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="560f1-115">特性</span><span class="sxs-lookup"><span data-stu-id="560f1-115">Attributes</span></span>  
  
|<span data-ttu-id="560f1-116">特性</span><span class="sxs-lookup"><span data-stu-id="560f1-116">Attribute</span></span>|<span data-ttu-id="560f1-117">描述</span><span class="sxs-lookup"><span data-stu-id="560f1-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="560f1-118">name</span><span class="sxs-lookup"><span data-stu-id="560f1-118">name</span></span>|<span data-ttu-id="560f1-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="560f1-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="560f1-120">子元素</span><span class="sxs-lookup"><span data-stu-id="560f1-120">Child Elements</span></span>  
 <span data-ttu-id="560f1-121">无。</span><span class="sxs-lookup"><span data-stu-id="560f1-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="560f1-122">父元素</span><span class="sxs-lookup"><span data-stu-id="560f1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="560f1-123">元素</span><span class="sxs-lookup"><span data-stu-id="560f1-123">Element</span></span>|<span data-ttu-id="560f1-124">描述</span><span class="sxs-lookup"><span data-stu-id="560f1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="560f1-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="560f1-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="560f1-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="560f1-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="560f1-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="560f1-127">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="560f1-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="560f1-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="560f1-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="560f1-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
