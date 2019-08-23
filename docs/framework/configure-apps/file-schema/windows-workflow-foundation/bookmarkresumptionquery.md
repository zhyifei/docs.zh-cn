---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: 9043deb66e1a4314df97f4da41103e74676a270c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945960"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="2d7a4-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="2d7a4-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="2d7a4-102">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="2d7a4-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="2d7a4-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="2d7a4-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="2d7a4-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="2d7a4-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="2d7a4-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2d7a4-105">\<system.serviceModel></span></span>  
<span data-ttu-id="2d7a4-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="2d7a4-106">\<tracking></span></span>  
<span data-ttu-id="2d7a4-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2d7a4-107">\<trackingProfile></span></span>  
<span data-ttu-id="2d7a4-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="2d7a4-108">\<workflow></span></span>  
<span data-ttu-id="2d7a4-109">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="2d7a4-109">\<bookmarkResumptionQueries></span></span>  
<span data-ttu-id="2d7a4-110">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="2d7a4-110">\<bookmarkResumptionQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d7a4-111">语法</span><span class="sxs-lookup"><span data-stu-id="2d7a4-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2d7a4-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2d7a4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="2d7a4-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2d7a4-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2d7a4-114">特性</span><span class="sxs-lookup"><span data-stu-id="2d7a4-114">Attributes</span></span>  
  
|<span data-ttu-id="2d7a4-115">特性</span><span class="sxs-lookup"><span data-stu-id="2d7a4-115">Attribute</span></span>|<span data-ttu-id="2d7a4-116">描述</span><span class="sxs-lookup"><span data-stu-id="2d7a4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2d7a4-117">NAME</span><span class="sxs-lookup"><span data-stu-id="2d7a4-117">name</span></span>|<span data-ttu-id="2d7a4-118">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="2d7a4-118">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2d7a4-119">子元素</span><span class="sxs-lookup"><span data-stu-id="2d7a4-119">Child Elements</span></span>  
 <span data-ttu-id="2d7a4-120">无。</span><span class="sxs-lookup"><span data-stu-id="2d7a4-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2d7a4-121">父元素</span><span class="sxs-lookup"><span data-stu-id="2d7a4-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2d7a4-122">元素</span><span class="sxs-lookup"><span data-stu-id="2d7a4-122">Element</span></span>|<span data-ttu-id="2d7a4-123">描述</span><span class="sxs-lookup"><span data-stu-id="2d7a4-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2d7a4-124">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="2d7a4-124">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="2d7a4-125">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="2d7a4-125">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2d7a4-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d7a4-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="2d7a4-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2d7a4-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="2d7a4-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="2d7a4-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
