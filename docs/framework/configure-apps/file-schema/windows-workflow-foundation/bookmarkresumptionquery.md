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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 821ded03ced33ee44c6588daefaf9049741abf8c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="71b81-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="71b81-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="71b81-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="71b81-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="71b81-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="71b81-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="71b81-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="71b81-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="71b81-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="71b81-106">\<system.serviceModel></span></span>  
<span data-ttu-id="71b81-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="71b81-107">\<tracking></span></span>  
<span data-ttu-id="71b81-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="71b81-108">\<trackingProfile></span></span>  
<span data-ttu-id="71b81-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="71b81-109">\<workflow></span></span>  
<span data-ttu-id="71b81-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="71b81-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="71b81-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="71b81-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71b81-112">语法</span><span class="sxs-lookup"><span data-stu-id="71b81-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71b81-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="71b81-113">Attributes and Elements</span></span>  
 <span data-ttu-id="71b81-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="71b81-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71b81-115">特性</span><span class="sxs-lookup"><span data-stu-id="71b81-115">Attributes</span></span>  
  
|<span data-ttu-id="71b81-116">特性</span><span class="sxs-lookup"><span data-stu-id="71b81-116">Attribute</span></span>|<span data-ttu-id="71b81-117">描述</span><span class="sxs-lookup"><span data-stu-id="71b81-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71b81-118">name</span><span class="sxs-lookup"><span data-stu-id="71b81-118">name</span></span>|<span data-ttu-id="71b81-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="71b81-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71b81-120">子元素</span><span class="sxs-lookup"><span data-stu-id="71b81-120">Child Elements</span></span>  
 <span data-ttu-id="71b81-121">无。</span><span class="sxs-lookup"><span data-stu-id="71b81-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="71b81-122">父元素</span><span class="sxs-lookup"><span data-stu-id="71b81-122">Parent Elements</span></span>  
  
|<span data-ttu-id="71b81-123">元素</span><span class="sxs-lookup"><span data-stu-id="71b81-123">Element</span></span>|<span data-ttu-id="71b81-124">描述</span><span class="sxs-lookup"><span data-stu-id="71b81-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71b81-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="71b81-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="71b81-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="71b81-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71b81-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="71b81-127">See Also</span></span>  
 <span data-ttu-id="71b81-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="71b81-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="71b81-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="71b81-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="71b81-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="71b81-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="71b81-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="71b81-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
