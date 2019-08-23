---
title: <cancelRequestedQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 7952520edbf799e5fab6864e50962c6ec2860928
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919649"
---
# <a name="cancelrequestedquery-of-wcf"></a><span data-ttu-id="c16b5-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="c16b5-102">\<cancelRequestedQuery> of WCF</span></span>

<span data-ttu-id="c16b5-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="c16b5-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c16b5-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="c16b5-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="c16b5-105">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="c16b5-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="c16b5-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c16b5-106">\<system.serviceModel></span></span>  
<span data-ttu-id="c16b5-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="c16b5-107">\<tracking></span></span>  
<span data-ttu-id="c16b5-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="c16b5-108">\<profiles></span></span>  
<span data-ttu-id="c16b5-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c16b5-109">\<trackingProfile></span></span>  
<span data-ttu-id="c16b5-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="c16b5-110">\<workflow></span></span>  
<span data-ttu-id="c16b5-111">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c16b5-111">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="c16b5-112">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="c16b5-112">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c16b5-113">语法</span><span class="sxs-lookup"><span data-stu-id="c16b5-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c16b5-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c16b5-114">Attributes and elements</span></span>

<span data-ttu-id="c16b5-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c16b5-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c16b5-116">特性</span><span class="sxs-lookup"><span data-stu-id="c16b5-116">Attributes</span></span>  
  
|<span data-ttu-id="c16b5-117">特性</span><span class="sxs-lookup"><span data-stu-id="c16b5-117">Attribute</span></span>|<span data-ttu-id="c16b5-118">描述</span><span class="sxs-lookup"><span data-stu-id="c16b5-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="c16b5-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c16b5-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|`childActivityName`|<span data-ttu-id="c16b5-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c16b5-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c16b5-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c16b5-121">Child elements</span></span>

<span data-ttu-id="c16b5-122">无。</span><span class="sxs-lookup"><span data-stu-id="c16b5-122">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="c16b5-123">父元素</span><span class="sxs-lookup"><span data-stu-id="c16b5-123">Parent elements</span></span>
  
|<span data-ttu-id="c16b5-124">元素</span><span class="sxs-lookup"><span data-stu-id="c16b5-124">Element</span></span>|<span data-ttu-id="c16b5-125">描述</span><span class="sxs-lookup"><span data-stu-id="c16b5-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c16b5-126">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="c16b5-126">\<cancelRequestedQueries></span></span>](cancelrequestedqueries-of-wcf.md)|<span data-ttu-id="c16b5-127">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="c16b5-127">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c16b5-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c16b5-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c16b5-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c16b5-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c16b5-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c16b5-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
