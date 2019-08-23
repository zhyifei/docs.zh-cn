---
title: <bookmarkResumptionQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: ee8457645a0b54e21ef27c2891ebea97d6cc547b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926354"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="aaa2e-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="aaa2e-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="aaa2e-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="aaa2e-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="aaa2e-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="aaa2e-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="aaa2e-105">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="aaa2e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="aaa2e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="aaa2e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="aaa2e-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="aaa2e-107">\<tracking></span></span>  
<span data-ttu-id="aaa2e-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="aaa2e-108">\<profiles></span></span>  
<span data-ttu-id="aaa2e-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="aaa2e-109">\<trackingProfile></span></span>  
<span data-ttu-id="aaa2e-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="aaa2e-110">\<workflow></span></span>  
<span data-ttu-id="aaa2e-111">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="aaa2e-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="aaa2e-112">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="aaa2e-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa2e-113">语法</span><span class="sxs-lookup"><span data-stu-id="aaa2e-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaa2e-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="aaa2e-114">Attributes and elements</span></span>

<span data-ttu-id="aaa2e-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="aaa2e-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaa2e-116">特性</span><span class="sxs-lookup"><span data-stu-id="aaa2e-116">Attributes</span></span>  
  
|<span data-ttu-id="aaa2e-117">特性</span><span class="sxs-lookup"><span data-stu-id="aaa2e-117">Attribute</span></span>|<span data-ttu-id="aaa2e-118">描述</span><span class="sxs-lookup"><span data-stu-id="aaa2e-118">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="aaa2e-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="aaa2e-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaa2e-120">子元素</span><span class="sxs-lookup"><span data-stu-id="aaa2e-120">Child elements</span></span>

<span data-ttu-id="aaa2e-121">无。</span><span class="sxs-lookup"><span data-stu-id="aaa2e-121">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="aaa2e-122">父元素</span><span class="sxs-lookup"><span data-stu-id="aaa2e-122">Parent elements</span></span>  
  
|<span data-ttu-id="aaa2e-123">元素</span><span class="sxs-lookup"><span data-stu-id="aaa2e-123">Element</span></span>|<span data-ttu-id="aaa2e-124">描述</span><span class="sxs-lookup"><span data-stu-id="aaa2e-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaa2e-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="aaa2e-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="aaa2e-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="aaa2e-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aaa2e-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="aaa2e-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="aaa2e-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="aaa2e-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="aaa2e-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="aaa2e-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
