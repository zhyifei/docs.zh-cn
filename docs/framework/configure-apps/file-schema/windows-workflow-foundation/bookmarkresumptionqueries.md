---
title: <bookmarkResumptionQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8ed61a7f-4254-439c-bdd8-b474971533f7
ms.openlocfilehash: 563e0cbd3f50887e1c9e3d47a3c9502acc13b2c9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398865"
---
# <a name="bookmarkresumptionqueries"></a><span data-ttu-id="260e7-101">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="260e7-101">\<bookmarkResumptionQueries></span></span>
<span data-ttu-id="260e7-102">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="260e7-102">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="260e7-103">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="260e7-103">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
 <span data-ttu-id="260e7-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="260e7-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="260e7-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="260e7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="260e7-106">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="260e7-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="260e7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="260e7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="260e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="260e7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="260e7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="260e7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="260e7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQueries >**</span><span class="sxs-lookup"><span data-stu-id="260e7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="260e7-111">语法</span><span class="sxs-lookup"><span data-stu-id="260e7-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="260e7-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="260e7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="260e7-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="260e7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="260e7-114">特性</span><span class="sxs-lookup"><span data-stu-id="260e7-114">Attributes</span></span>  
 <span data-ttu-id="260e7-115">无。</span><span class="sxs-lookup"><span data-stu-id="260e7-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="260e7-116">子元素</span><span class="sxs-lookup"><span data-stu-id="260e7-116">Child Elements</span></span>  
  
|<span data-ttu-id="260e7-117">元素</span><span class="sxs-lookup"><span data-stu-id="260e7-117">Element</span></span>|<span data-ttu-id="260e7-118">描述</span><span class="sxs-lookup"><span data-stu-id="260e7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="260e7-119">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="260e7-119">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery.md)|<span data-ttu-id="260e7-120">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="260e7-120">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="260e7-121">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="260e7-121">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="260e7-122">父元素</span><span class="sxs-lookup"><span data-stu-id="260e7-122">Parent Elements</span></span>  
  
|<span data-ttu-id="260e7-123">元素</span><span class="sxs-lookup"><span data-stu-id="260e7-123">Element</span></span>|<span data-ttu-id="260e7-124">描述</span><span class="sxs-lookup"><span data-stu-id="260e7-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="260e7-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="260e7-125">\<workflow></span></span>](workflow.md)|<span data-ttu-id="260e7-126">一个配置元素，该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="260e7-126">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="260e7-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="260e7-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="260e7-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="260e7-128">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="260e7-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="260e7-129">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
