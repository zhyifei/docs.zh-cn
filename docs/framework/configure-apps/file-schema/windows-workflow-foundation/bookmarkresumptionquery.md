---
title: '&lt;bookmarkResumptionQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e52b4ef5104397d3c4b8abc89a1d637b17fcde9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="cfd32-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="cfd32-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="cfd32-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="cfd32-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="cfd32-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="cfd32-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="cfd32-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="cfd32-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="cfd32-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="cfd32-106">\<system.serviceModel></span></span>  
<span data-ttu-id="cfd32-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="cfd32-107">\<tracking></span></span>  
<span data-ttu-id="cfd32-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="cfd32-108">\<trackingProfile></span></span>  
<span data-ttu-id="cfd32-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="cfd32-109">\<workflow></span></span>  
<span data-ttu-id="cfd32-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="cfd32-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="cfd32-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="cfd32-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfd32-112">语法</span><span class="sxs-lookup"><span data-stu-id="cfd32-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cfd32-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cfd32-113">Attributes and Elements</span></span>  
 <span data-ttu-id="cfd32-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cfd32-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cfd32-115">特性</span><span class="sxs-lookup"><span data-stu-id="cfd32-115">Attributes</span></span>  
  
|<span data-ttu-id="cfd32-116">特性</span><span class="sxs-lookup"><span data-stu-id="cfd32-116">Attribute</span></span>|<span data-ttu-id="cfd32-117">描述</span><span class="sxs-lookup"><span data-stu-id="cfd32-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cfd32-118">name</span><span class="sxs-lookup"><span data-stu-id="cfd32-118">name</span></span>|<span data-ttu-id="cfd32-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="cfd32-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cfd32-120">子元素</span><span class="sxs-lookup"><span data-stu-id="cfd32-120">Child Elements</span></span>  
 <span data-ttu-id="cfd32-121">无。</span><span class="sxs-lookup"><span data-stu-id="cfd32-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cfd32-122">父元素</span><span class="sxs-lookup"><span data-stu-id="cfd32-122">Parent Elements</span></span>  
  
|<span data-ttu-id="cfd32-123">元素</span><span class="sxs-lookup"><span data-stu-id="cfd32-123">Element</span></span>|<span data-ttu-id="cfd32-124">描述</span><span class="sxs-lookup"><span data-stu-id="cfd32-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cfd32-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="cfd32-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="cfd32-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="cfd32-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cfd32-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cfd32-127">See Also</span></span>  
 <span data-ttu-id="cfd32-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cfd32-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="cfd32-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="cfd32-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="cfd32-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="cfd32-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="cfd32-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="cfd32-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
