---
title: "WCF 的 &lt;bookmarkResumptionQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c29f4c0cd92b2c4e8263e1893e7deefc2f14624a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionqueriesgt-of-wcf"></a><span data-ttu-id="02d9c-102">WCF 的 &lt;bookmarkResumptionQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="02d9c-102">&lt;bookmarkResumptionQueries&gt; of WCF</span></span>
<span data-ttu-id="02d9c-103">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="02d9c-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="02d9c-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="02d9c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="02d9c-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="02d9c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="02d9c-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="02d9c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="02d9c-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="02d9c-107">\<tracking></span></span>  
<span data-ttu-id="02d9c-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="02d9c-108">\<trackingProfile></span></span>  
<span data-ttu-id="02d9c-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="02d9c-109">\<workflow></span></span>  
<span data-ttu-id="02d9c-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="02d9c-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="02d9c-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="02d9c-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02d9c-112">语法</span><span class="sxs-lookup"><span data-stu-id="02d9c-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="02d9c-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02d9c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="02d9c-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02d9c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02d9c-115">特性</span><span class="sxs-lookup"><span data-stu-id="02d9c-115">Attributes</span></span>  
 <span data-ttu-id="02d9c-116">无。</span><span class="sxs-lookup"><span data-stu-id="02d9c-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="02d9c-117">子元素</span><span class="sxs-lookup"><span data-stu-id="02d9c-117">Child Elements</span></span>  
  
|<span data-ttu-id="02d9c-118">元素</span><span class="sxs-lookup"><span data-stu-id="02d9c-118">Element</span></span>|<span data-ttu-id="02d9c-119">描述</span><span class="sxs-lookup"><span data-stu-id="02d9c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02d9c-120">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="02d9c-120">\<bookmarkResumptionQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionquery.md)|<span data-ttu-id="02d9c-121">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="02d9c-121">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="02d9c-122">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="02d9c-122">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02d9c-123">父元素</span><span class="sxs-lookup"><span data-stu-id="02d9c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="02d9c-124">元素</span><span class="sxs-lookup"><span data-stu-id="02d9c-124">Element</span></span>|<span data-ttu-id="02d9c-125">描述</span><span class="sxs-lookup"><span data-stu-id="02d9c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02d9c-126">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="02d9c-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="02d9c-127">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="02d9c-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02d9c-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="02d9c-128">See Also</span></span>  
 <span data-ttu-id="02d9c-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="02d9c-129"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="02d9c-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="02d9c-130"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="02d9c-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="02d9c-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="02d9c-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="02d9c-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
