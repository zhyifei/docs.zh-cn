---
title: WCF 的 &lt;cancelRequestedQuery&gt;
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 72fd23097760375738c2116b4535940873436986
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498263"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="ef1f4-102">WCF 的 &lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="ef1f4-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>

<span data-ttu-id="ef1f4-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="ef1f4-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="ef1f4-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="ef1f4-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ef1f4-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ef1f4-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ef1f4-107">\<tracking></span></span>  
<span data-ttu-id="ef1f4-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="ef1f4-108">\<profiles></span></span>  
<span data-ttu-id="ef1f4-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ef1f4-109">\<trackingProfile></span></span>  
<span data-ttu-id="ef1f4-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ef1f4-110">\<workflow></span></span>  
<span data-ttu-id="ef1f4-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="ef1f4-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="ef1f4-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="ef1f4-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef1f4-113">语法</span><span class="sxs-lookup"><span data-stu-id="ef1f4-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef1f4-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ef1f4-114">Attributes and elements</span></span>

<span data-ttu-id="ef1f4-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef1f4-116">特性</span><span class="sxs-lookup"><span data-stu-id="ef1f4-116">Attributes</span></span>  
  
|<span data-ttu-id="ef1f4-117">特性</span><span class="sxs-lookup"><span data-stu-id="ef1f4-117">Attribute</span></span>|<span data-ttu-id="ef1f4-118">描述</span><span class="sxs-lookup"><span data-stu-id="ef1f4-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="ef1f4-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="ef1f4-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef1f4-121">子元素</span><span class="sxs-lookup"><span data-stu-id="ef1f4-121">Child elements</span></span>

<span data-ttu-id="ef1f4-122">无。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="ef1f4-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ef1f4-123">Parent elements</span></span>
  
|<span data-ttu-id="ef1f4-124">元素</span><span class="sxs-lookup"><span data-stu-id="ef1f4-124">Element</span></span>|<span data-ttu-id="ef1f4-125">描述</span><span class="sxs-lookup"><span data-stu-id="ef1f4-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef1f4-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="ef1f4-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="ef1f4-127">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="ef1f4-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef1f4-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef1f4-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ef1f4-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ef1f4-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ef1f4-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ef1f4-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
