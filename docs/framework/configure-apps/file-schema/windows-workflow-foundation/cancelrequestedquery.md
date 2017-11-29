---
title: '&lt;cancelRequestedQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e1697b245f9ab61cab3e4b26b1756259f0eba9f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="fc2d8-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="fc2d8-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="fc2d8-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="fc2d8-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="fc2d8-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="fc2d8-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-106">\<system.serviceModel></span></span>  
<span data-ttu-id="fc2d8-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-107">\<tracking></span></span>  
<span data-ttu-id="fc2d8-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-108">\<trackingProfile></span></span>  
<span data-ttu-id="fc2d8-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-109">\<workflow></span></span>  
<span data-ttu-id="fc2d8-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="fc2d8-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc2d8-112">语法</span><span class="sxs-lookup"><span data-stu-id="fc2d8-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc2d8-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="fc2d8-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fc2d8-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc2d8-115">特性</span><span class="sxs-lookup"><span data-stu-id="fc2d8-115">Attributes</span></span>  
  
|<span data-ttu-id="fc2d8-116">特性</span><span class="sxs-lookup"><span data-stu-id="fc2d8-116">Attribute</span></span>|<span data-ttu-id="fc2d8-117">描述</span><span class="sxs-lookup"><span data-stu-id="fc2d8-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc2d8-118">activityName</span><span class="sxs-lookup"><span data-stu-id="fc2d8-118">activityName</span></span>|<span data-ttu-id="fc2d8-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="fc2d8-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="fc2d8-120">childActivityName</span></span>|<span data-ttu-id="fc2d8-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc2d8-122">子元素</span><span class="sxs-lookup"><span data-stu-id="fc2d8-122">Child Elements</span></span>  
 <span data-ttu-id="fc2d8-123">无。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc2d8-124">父元素</span><span class="sxs-lookup"><span data-stu-id="fc2d8-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fc2d8-125">元素</span><span class="sxs-lookup"><span data-stu-id="fc2d8-125">Element</span></span>|<span data-ttu-id="fc2d8-126">描述</span><span class="sxs-lookup"><span data-stu-id="fc2d8-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc2d8-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="fc2d8-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="fc2d8-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="fc2d8-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="fc2d8-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fc2d8-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc2d8-130">See Also</span></span>  
 <span data-ttu-id="fc2d8-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fc2d8-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="fc2d8-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="fc2d8-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="fc2d8-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="fc2d8-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="fc2d8-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="fc2d8-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
