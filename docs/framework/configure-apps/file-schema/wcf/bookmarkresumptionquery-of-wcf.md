---
title: <bookmarkResumptionQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 755a34f0-87c9-4a1e-ae4d-0fb8a6fbdc0e
ms.openlocfilehash: 36d169b78e78692c7b45c75d5d375bddbba1c66f
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850100"
---
# <a name="bookmarkresumptionquery-of-wcf"></a><span data-ttu-id="efa1f-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="efa1f-102">\<bookmarkResumptionQuery> of WCF</span></span>

<span data-ttu-id="efa1f-103">表示一个查询，该查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="efa1f-103">Represents a query that is used to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="efa1f-104">跟踪参与者需要用此查询来订阅书签恢复记录。</span><span class="sxs-lookup"><span data-stu-id="efa1f-104">The query is necessary for a tracking participant to subscribe to bookmark resumption records.</span></span>  
  
<span data-ttu-id="efa1f-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>
  
<span data-ttu-id="efa1f-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="efa1f-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="efa1f-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="efa1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="efa1f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="efa1f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="efa1f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="efa1f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bookmarkResumptionQueries >** ](bookmarkresumptionqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="efa1f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<bookmarkResumptionQueries>**](bookmarkresumptionqueries-of-wcf.md)</span></span>\
<span data-ttu-id="efa1f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="efa1f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<bookmarkResumptionQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efa1f-114">语法</span><span class="sxs-lookup"><span data-stu-id="efa1f-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="efa1f-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="efa1f-115">Attributes and elements</span></span>

<span data-ttu-id="efa1f-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="efa1f-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="efa1f-117">特性</span><span class="sxs-lookup"><span data-stu-id="efa1f-117">Attributes</span></span>  
  
|<span data-ttu-id="efa1f-118">特性</span><span class="sxs-lookup"><span data-stu-id="efa1f-118">Attribute</span></span>|<span data-ttu-id="efa1f-119">描述</span><span class="sxs-lookup"><span data-stu-id="efa1f-119">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="efa1f-120">一个字符串，指定要订阅的书签记录的名称。</span><span class="sxs-lookup"><span data-stu-id="efa1f-120">A string that specifies the name of the bookmark record to subscribe to.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="efa1f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="efa1f-121">Child elements</span></span>

<span data-ttu-id="efa1f-122">无。</span><span class="sxs-lookup"><span data-stu-id="efa1f-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="efa1f-123">父元素</span><span class="sxs-lookup"><span data-stu-id="efa1f-123">Parent elements</span></span>  
  
|<span data-ttu-id="efa1f-124">元素</span><span class="sxs-lookup"><span data-stu-id="efa1f-124">Element</span></span>|<span data-ttu-id="efa1f-125">描述</span><span class="sxs-lookup"><span data-stu-id="efa1f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="efa1f-126">\<bookmarkResumptionQueries></span><span class="sxs-lookup"><span data-stu-id="efa1f-126">\<bookmarkResumptionQueries></span></span>](bookmarkresumptionqueries-of-wcf.md)|<span data-ttu-id="efa1f-127">表示一个查询集合，这些查询用于跟踪工作流实例中的书签恢复。</span><span class="sxs-lookup"><span data-stu-id="efa1f-127">Represents a collection of queries that are used to track resumption of a bookmark within a workflow instance.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="efa1f-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="efa1f-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.BookmarkResumptionQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.BookmarkResumptionQuery?displayProperty=nameWithType>
- [<span data-ttu-id="efa1f-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="efa1f-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="efa1f-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="efa1f-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
