---
title: <bookmarkResumptionQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: ed086712-1dc7-4932-a592-d1116a0155f3
ms.openlocfilehash: 94ff9f44f295b45c03e1bd8f52a85d6b7b0c6e3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850138"
---
# <a name="bookmarkresumptionqueries-of-wcf"></a><span data-ttu-id="bd9c9-102">\<WCF 的 bookmarkResumptionQueries ></span><span class="sxs-lookup"><span data-stu-id="bd9c9-102">\<bookmarkResumptionQueries> of WCF</span></span>
  
<span data-ttu-id="bd9c9-103">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-103">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="bd9c9-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="bd9c9-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="bd9c9-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bd9c9-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bd9c9-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bd9c9-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bd9c9-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bd9c9-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="bd9c9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="bd9c9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="bd9c9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bd9c9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="bd9c9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="bd9c9-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="bd9c9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<bookmarkResumptionQueries >**</span><span class="sxs-lookup"><span data-stu-id="bd9c9-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="bd9c9-113">语法</span><span class="sxs-lookup"><span data-stu-id="bd9c9-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bd9c9-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="bd9c9-114">Attributes and elements</span></span>  
  
<span data-ttu-id="bd9c9-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bd9c9-116">特性</span><span class="sxs-lookup"><span data-stu-id="bd9c9-116">Attributes</span></span>  
  
<span data-ttu-id="bd9c9-117">无。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bd9c9-118">子元素</span><span class="sxs-lookup"><span data-stu-id="bd9c9-118">Child elements</span></span>  
  
|<span data-ttu-id="bd9c9-119">元素</span><span class="sxs-lookup"><span data-stu-id="bd9c9-119">Element</span></span>|<span data-ttu-id="bd9c9-120">描述</span><span class="sxs-lookup"><span data-stu-id="bd9c9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd9c9-121">\<bookmarkResumptionQuery></span><span class="sxs-lookup"><span data-stu-id="bd9c9-121">\<bookmarkResumptionQuery></span></span>](bookmarkresumptionquery-of-wcf.md)|<span data-ttu-id="bd9c9-122">一个查询，用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-122">A query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="bd9c9-123">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-123">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bd9c9-124">父元素</span><span class="sxs-lookup"><span data-stu-id="bd9c9-124">Parent elements</span></span>  
  
|<span data-ttu-id="bd9c9-125">元素</span><span class="sxs-lookup"><span data-stu-id="bd9c9-125">Element</span></span>|<span data-ttu-id="bd9c9-126">描述</span><span class="sxs-lookup"><span data-stu-id="bd9c9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bd9c9-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="bd9c9-127">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="bd9c9-128">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="bd9c9-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bd9c9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd9c9-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="bd9c9-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="bd9c9-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="bd9c9-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="bd9c9-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
