---
title: <cancelRequestedQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 0ac8b87afc44927ab6653dd6fcdc09cd61436a9b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850051"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="a8e82-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="a8e82-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="a8e82-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="a8e82-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="a8e82-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="a8e82-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="a8e82-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a8e82-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="a8e82-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a8e82-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a8e82-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a8e82-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a8e82-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8e82-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="a8e82-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="a8e82-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="a8e82-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8e82-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="a8e82-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8e82-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="a8e82-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<q >** ](cancelrequestedqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="a8e82-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries-of-wcf.md)</span></span>\
<span data-ttu-id="a8e82-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="a8e82-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="a8e82-114">语法</span><span class="sxs-lookup"><span data-stu-id="a8e82-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestedQueries>
          <cancelRequestedQuery activityName="String"
                                childActivityName="String" />
        </cancelRequestedQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8e82-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a8e82-115">Attributes and elements</span></span>

<span data-ttu-id="a8e82-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a8e82-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a8e82-117">特性</span><span class="sxs-lookup"><span data-stu-id="a8e82-117">Attributes</span></span>  
  
|<span data-ttu-id="a8e82-118">特性</span><span class="sxs-lookup"><span data-stu-id="a8e82-118">Attribute</span></span>|<span data-ttu-id="a8e82-119">描述</span><span class="sxs-lookup"><span data-stu-id="a8e82-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="a8e82-120">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="a8e82-120">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="a8e82-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="a8e82-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a8e82-122">子元素</span><span class="sxs-lookup"><span data-stu-id="a8e82-122">Child elements</span></span>

<span data-ttu-id="a8e82-123">无。</span><span class="sxs-lookup"><span data-stu-id="a8e82-123">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="a8e82-124">父元素</span><span class="sxs-lookup"><span data-stu-id="a8e82-124">Parent elements</span></span>
  
|<span data-ttu-id="a8e82-125">元素</span><span class="sxs-lookup"><span data-stu-id="a8e82-125">Element</span></span>|<span data-ttu-id="a8e82-126">描述</span><span class="sxs-lookup"><span data-stu-id="a8e82-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a8e82-127">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="a8e82-127">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="a8e82-128">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="a8e82-128">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8e82-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8e82-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="a8e82-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="a8e82-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="a8e82-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a8e82-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
