---
title: WCF 的 &lt;bookmarkResumptionQueries&gt;
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: ba8c98557a859f4bd37b9aaca80a44c393429da4
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146077"
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="15186-102">WCF 的 &lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="15186-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
  
<span data-ttu-id="15186-103">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="15186-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="15186-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="15186-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="15186-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="15186-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="15186-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="15186-106">\<system.serviceModel></span></span>  
<span data-ttu-id="15186-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="15186-107">\<tracking></span></span>  
<span data-ttu-id="15186-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="15186-108">\<profiles></span></span>  
<span data-ttu-id="15186-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="15186-109">\<trackingProfile></span></span>  
<span data-ttu-id="15186-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="15186-110">\<workflow></span></span>  
<span data-ttu-id="15186-111">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="15186-111">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="15186-112">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="15186-112">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15186-113">语法</span><span class="sxs-lookup"><span data-stu-id="15186-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15186-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="15186-114">Attributes and elements</span></span>  
  
<span data-ttu-id="15186-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="15186-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15186-116">特性</span><span class="sxs-lookup"><span data-stu-id="15186-116">Attributes</span></span>  
  
<span data-ttu-id="15186-117">无。</span><span class="sxs-lookup"><span data-stu-id="15186-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15186-118">子元素</span><span class="sxs-lookup"><span data-stu-id="15186-118">Child elements</span></span>  
  
|<span data-ttu-id="15186-119">元素</span><span class="sxs-lookup"><span data-stu-id="15186-119">Element</span></span>|<span data-ttu-id="15186-120">描述</span><span class="sxs-lookup"><span data-stu-id="15186-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15186-121">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="15186-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="15186-122">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="15186-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="15186-123">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="15186-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="15186-124">父元素</span><span class="sxs-lookup"><span data-stu-id="15186-124">Parent elements</span></span>  
  
|<span data-ttu-id="15186-125">元素</span><span class="sxs-lookup"><span data-stu-id="15186-125">Element</span></span>|<span data-ttu-id="15186-126">描述</span><span class="sxs-lookup"><span data-stu-id="15186-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15186-127">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="15186-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="15186-128">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="15186-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="15186-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="15186-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType> 
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="15186-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="15186-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="15186-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="15186-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
