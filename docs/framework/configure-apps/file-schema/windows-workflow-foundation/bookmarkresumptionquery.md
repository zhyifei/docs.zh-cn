---
title: <bookmarkResumptionQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 226de75d-d25c-48d5-b069-4b7d80a6852b
ms.openlocfilehash: b2a81a42a17474bdb0124bec6d3c3eeefa514411
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398849"
---
# <a name="bookmarkresumptionquery"></a><span data-ttu-id="e790f-101">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="e790f-101">\<bookmarkResumptionQuery></span></span>
<span data-ttu-id="e790f-102">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="e790f-102">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="e790f-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="e790f-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="e790f-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e790f-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e790f-106">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="e790f-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="e790f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="e790f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="e790f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bookmarkResumptionQueries >** ](bookmarkresumptionqueries.md)</span><span class="sxs-lookup"><span data-stu-id="e790f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries.md)</span></span>\
<span data-ttu-id="e790f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="e790f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e790f-112">语法</span><span class="sxs-lookup"><span data-stu-id="e790f-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e790f-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e790f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e790f-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e790f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e790f-115">特性</span><span class="sxs-lookup"><span data-stu-id="e790f-115">Attributes</span></span>  
  
|<span data-ttu-id="e790f-116">特性</span><span class="sxs-lookup"><span data-stu-id="e790f-116">Attribute</span></span>|<span data-ttu-id="e790f-117">描述</span><span class="sxs-lookup"><span data-stu-id="e790f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e790f-118">NAME</span><span class="sxs-lookup"><span data-stu-id="e790f-118">name</span></span>|<span data-ttu-id="e790f-119">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="e790f-119">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e790f-120">子元素</span><span class="sxs-lookup"><span data-stu-id="e790f-120">Child Elements</span></span>  
 <span data-ttu-id="e790f-121">无。</span><span class="sxs-lookup"><span data-stu-id="e790f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e790f-122">父元素</span><span class="sxs-lookup"><span data-stu-id="e790f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e790f-123">元素</span><span class="sxs-lookup"><span data-stu-id="e790f-123">Element</span></span>|<span data-ttu-id="e790f-124">描述</span><span class="sxs-lookup"><span data-stu-id="e790f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e790f-125">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="e790f-125">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries.md)|<span data-ttu-id="e790f-126">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="e790f-126">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e790f-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e790f-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="e790f-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e790f-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="e790f-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e790f-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
