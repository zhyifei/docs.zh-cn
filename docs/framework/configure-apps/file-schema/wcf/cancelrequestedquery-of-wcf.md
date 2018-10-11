---
title: WCF 的 &lt;cancelRequestedQuery&gt;
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 38d946a213131e8dcb6f4100d0ad67f7c167f342
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086396"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="e35ae-102">WCF 的 &lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="e35ae-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="e35ae-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="e35ae-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e35ae-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="e35ae-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="e35ae-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="e35ae-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="e35ae-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e35ae-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e35ae-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e35ae-107">\<tracking></span></span>  
<span data-ttu-id="e35ae-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e35ae-108">\<trackingProfile></span></span>  
<span data-ttu-id="e35ae-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e35ae-109">\<workflow></span></span>  
<span data-ttu-id="e35ae-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="e35ae-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="e35ae-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="e35ae-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e35ae-112">语法</span><span class="sxs-lookup"><span data-stu-id="e35ae-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String"
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e35ae-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e35ae-113">Attributes and Elements</span></span>  
 <span data-ttu-id="e35ae-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e35ae-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e35ae-115">特性</span><span class="sxs-lookup"><span data-stu-id="e35ae-115">Attributes</span></span>  
  
|<span data-ttu-id="e35ae-116">特性</span><span class="sxs-lookup"><span data-stu-id="e35ae-116">Attribute</span></span>|<span data-ttu-id="e35ae-117">描述</span><span class="sxs-lookup"><span data-stu-id="e35ae-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e35ae-118">activityName</span><span class="sxs-lookup"><span data-stu-id="e35ae-118">activityName</span></span>|<span data-ttu-id="e35ae-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="e35ae-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="e35ae-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="e35ae-120">childActivityName</span></span>|<span data-ttu-id="e35ae-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="e35ae-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e35ae-122">子元素</span><span class="sxs-lookup"><span data-stu-id="e35ae-122">Child Elements</span></span>  
 <span data-ttu-id="e35ae-123">无。</span><span class="sxs-lookup"><span data-stu-id="e35ae-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e35ae-124">父元素</span><span class="sxs-lookup"><span data-stu-id="e35ae-124">Parent Elements</span></span>  
  
|<span data-ttu-id="e35ae-125">元素</span><span class="sxs-lookup"><span data-stu-id="e35ae-125">Element</span></span>|<span data-ttu-id="e35ae-126">描述</span><span class="sxs-lookup"><span data-stu-id="e35ae-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e35ae-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="e35ae-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="e35ae-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="e35ae-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e35ae-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="e35ae-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e35ae-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="e35ae-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="e35ae-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e35ae-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e35ae-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e35ae-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
