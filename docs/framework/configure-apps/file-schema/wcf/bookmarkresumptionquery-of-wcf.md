---
title: WCF 的 &lt;bookmarkResumptionQuery&gt;
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 6463404e17edff8eb1efe3f96e44b5b9997ffca3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147806"
---
# <a name="ltbookmarkresumptionquerygt-of-wcf"></a><span data-ttu-id="62fa5-102">WCF 的 &lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="62fa5-102">&lt;bookmarkResumptionQuery&gt; of WCF</span></span>

<span data-ttu-id="62fa5-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="62fa5-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="62fa5-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="62fa5-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="62fa5-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="62fa5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="62fa5-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62fa5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="62fa5-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="62fa5-107">\<tracking></span></span>  
<span data-ttu-id="62fa5-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="62fa5-108">\<profiles></span></span>  
<span data-ttu-id="62fa5-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="62fa5-109">\<trackingProfile></span></span>  
<span data-ttu-id="62fa5-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="62fa5-110">\<workflow></span></span>  
<span data-ttu-id="62fa5-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="62fa5-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="62fa5-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="62fa5-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62fa5-113">语法</span><span class="sxs-lookup"><span data-stu-id="62fa5-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <bookmarkResumptionQueries>
          <bookmarkResumptionQuery name="String" />
        </bookmarkResumptionQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62fa5-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="62fa5-114">Attributes and elements</span></span>

<span data-ttu-id="62fa5-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="62fa5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62fa5-116">特性</span><span class="sxs-lookup"><span data-stu-id="62fa5-116">Attributes</span></span>  
  
|<span data-ttu-id="62fa5-117">特性</span><span class="sxs-lookup"><span data-stu-id="62fa5-117">Attribute</span></span>|<span data-ttu-id="62fa5-118">描述</span><span class="sxs-lookup"><span data-stu-id="62fa5-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="62fa5-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="62fa5-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62fa5-120">子元素</span><span class="sxs-lookup"><span data-stu-id="62fa5-120">Child elements</span></span>

<span data-ttu-id="62fa5-121">无。</span><span class="sxs-lookup"><span data-stu-id="62fa5-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="62fa5-122">父元素</span><span class="sxs-lookup"><span data-stu-id="62fa5-122">Parent elements</span></span>  
  
|<span data-ttu-id="62fa5-123">元素</span><span class="sxs-lookup"><span data-stu-id="62fa5-123">Element</span></span>|<span data-ttu-id="62fa5-124">描述</span><span class="sxs-lookup"><span data-stu-id="62fa5-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62fa5-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="62fa5-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="62fa5-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="62fa5-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62fa5-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="62fa5-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="62fa5-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="62fa5-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="62fa5-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="62fa5-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
