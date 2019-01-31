---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 7fb298bcbc5b4bf5d699d3c79936ca3c15f67c0e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268179"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="8e6ea-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="8e6ea-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="8e6ea-102">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="8e6ea-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="8e6ea-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="8e6ea-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="8e6ea-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8e6ea-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8e6ea-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8e6ea-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8e6ea-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8e6ea-106">\<tracking></span></span>  
<span data-ttu-id="8e6ea-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8e6ea-107">\<trackingProfile></span></span>  
<span data-ttu-id="8e6ea-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8e6ea-108">\<workflow></span></span>  
<span data-ttu-id="8e6ea-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="8e6ea-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="8e6ea-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="8e6ea-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e6ea-111">语法</span><span class="sxs-lookup"><span data-stu-id="8e6ea-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e6ea-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8e6ea-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8e6ea-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8e6ea-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e6ea-114">特性</span><span class="sxs-lookup"><span data-stu-id="8e6ea-114">Attributes</span></span>  
  
|<span data-ttu-id="8e6ea-115">特性</span><span class="sxs-lookup"><span data-stu-id="8e6ea-115">Attribute</span></span>|<span data-ttu-id="8e6ea-116">描述</span><span class="sxs-lookup"><span data-stu-id="8e6ea-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e6ea-117">name</span><span class="sxs-lookup"><span data-stu-id="8e6ea-117">name</span></span>|<span data-ttu-id="8e6ea-118">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="8e6ea-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e6ea-119">子元素</span><span class="sxs-lookup"><span data-stu-id="8e6ea-119">Child Elements</span></span>  
 <span data-ttu-id="8e6ea-120">无。</span><span class="sxs-lookup"><span data-stu-id="8e6ea-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e6ea-121">父元素</span><span class="sxs-lookup"><span data-stu-id="8e6ea-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8e6ea-122">元素</span><span class="sxs-lookup"><span data-stu-id="8e6ea-122">Element</span></span>|<span data-ttu-id="8e6ea-123">描述</span><span class="sxs-lookup"><span data-stu-id="8e6ea-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e6ea-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="8e6ea-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="8e6ea-125">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="8e6ea-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e6ea-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e6ea-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8e6ea-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8e6ea-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8e6ea-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8e6ea-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
