---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: e43ba66e2c3ccfbb723b1eea8ef6774ad3f9f2aa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140031"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="a1ce1-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a1ce1-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="a1ce1-102">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="a1ce1-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="a1ce1-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="a1ce1-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="a1ce1-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a1ce1-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a1ce1-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a1ce1-105">\<system.serviceModel></span></span>  
<span data-ttu-id="a1ce1-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="a1ce1-106">\<tracking></span></span>  
<span data-ttu-id="a1ce1-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a1ce1-107">\<trackingProfile></span></span>  
<span data-ttu-id="a1ce1-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="a1ce1-108">\<workflow></span></span>  
<span data-ttu-id="a1ce1-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a1ce1-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="a1ce1-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="a1ce1-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1ce1-111">语法</span><span class="sxs-lookup"><span data-stu-id="a1ce1-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1ce1-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a1ce1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a1ce1-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a1ce1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1ce1-114">特性</span><span class="sxs-lookup"><span data-stu-id="a1ce1-114">Attributes</span></span>  
  
|<span data-ttu-id="a1ce1-115">特性</span><span class="sxs-lookup"><span data-stu-id="a1ce1-115">Attribute</span></span>|<span data-ttu-id="a1ce1-116">描述</span><span class="sxs-lookup"><span data-stu-id="a1ce1-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a1ce1-117">name</span><span class="sxs-lookup"><span data-stu-id="a1ce1-117">name</span></span>|<span data-ttu-id="a1ce1-118">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="a1ce1-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1ce1-119">子元素</span><span class="sxs-lookup"><span data-stu-id="a1ce1-119">Child Elements</span></span>  
 <span data-ttu-id="a1ce1-120">无。</span><span class="sxs-lookup"><span data-stu-id="a1ce1-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1ce1-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a1ce1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a1ce1-122">元素</span><span class="sxs-lookup"><span data-stu-id="a1ce1-122">Element</span></span>|<span data-ttu-id="a1ce1-123">描述</span><span class="sxs-lookup"><span data-stu-id="a1ce1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a1ce1-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="a1ce1-124">\<bookmarkResumptionQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bookmarkresumptionqueries.md)|<span data-ttu-id="a1ce1-125">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="a1ce1-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a1ce1-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a1ce1-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a1ce1-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="a1ce1-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a1ce1-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a1ce1-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
