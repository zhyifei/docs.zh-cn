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
ms.openlocfilehash: bafb044d052692385e0be0f4dbb1271eca847b1a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbookmarkresumptionquerygt"></a><span data-ttu-id="3343c-102">&lt;bookmarkResumptionQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3343c-102">&lt;bookmarkResumptionQuery&gt;</span></span>
<span data-ttu-id="3343c-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="3343c-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="3343c-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="3343c-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="3343c-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="3343c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="3343c-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3343c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="3343c-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="3343c-107">\<tracking></span></span>  
<span data-ttu-id="3343c-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3343c-108">\<trackingProfile></span></span>  
<span data-ttu-id="3343c-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="3343c-109">\<workflow></span></span>  
<span data-ttu-id="3343c-110">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="3343c-110">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="3343c-111">\<bookmarkResumptionQuery ></span><span class="sxs-lookup"><span data-stu-id="3343c-111">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3343c-112">语法</span><span class="sxs-lookup"><span data-stu-id="3343c-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3343c-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3343c-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3343c-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3343c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3343c-115">特性</span><span class="sxs-lookup"><span data-stu-id="3343c-115">Attributes</span></span>  
  
|<span data-ttu-id="3343c-116">特性</span><span class="sxs-lookup"><span data-stu-id="3343c-116">Attribute</span></span>|<span data-ttu-id="3343c-117">描述</span><span class="sxs-lookup"><span data-stu-id="3343c-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3343c-118">name</span><span class="sxs-lookup"><span data-stu-id="3343c-118">name</span></span>|<span data-ttu-id="3343c-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="3343c-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3343c-120">子元素</span><span class="sxs-lookup"><span data-stu-id="3343c-120">Child Elements</span></span>  
 <span data-ttu-id="3343c-121">无。</span><span class="sxs-lookup"><span data-stu-id="3343c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3343c-122">父元素</span><span class="sxs-lookup"><span data-stu-id="3343c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="3343c-123">元素</span><span class="sxs-lookup"><span data-stu-id="3343c-123">Element</span></span>|<span data-ttu-id="3343c-124">描述</span><span class="sxs-lookup"><span data-stu-id="3343c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3343c-125">\<bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="3343c-125">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="3343c-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="3343c-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3343c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3343c-127">See Also</span></span>  
 <span data-ttu-id="3343c-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3343c-128"><xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3343c-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3343c-129"><xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3343c-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="3343c-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3343c-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="3343c-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
