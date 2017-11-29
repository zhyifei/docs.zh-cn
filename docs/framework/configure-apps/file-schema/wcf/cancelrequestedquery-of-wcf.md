---
title: "WCF 的 &lt;cancelRequestedQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab16fe138701d180f528b5ec07e106acd53023b8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="d0afd-102">WCF 的 &lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="d0afd-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="d0afd-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="d0afd-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d0afd-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="d0afd-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d0afd-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="d0afd-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="d0afd-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d0afd-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d0afd-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="d0afd-107">\<tracking></span></span>  
<span data-ttu-id="d0afd-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d0afd-108">\<trackingProfile></span></span>  
<span data-ttu-id="d0afd-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="d0afd-109">\<workflow></span></span>  
<span data-ttu-id="d0afd-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="d0afd-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="d0afd-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="d0afd-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0afd-112">语法</span><span class="sxs-lookup"><span data-stu-id="d0afd-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d0afd-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d0afd-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d0afd-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d0afd-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0afd-115">特性</span><span class="sxs-lookup"><span data-stu-id="d0afd-115">Attributes</span></span>  
  
|<span data-ttu-id="d0afd-116">特性</span><span class="sxs-lookup"><span data-stu-id="d0afd-116">Attribute</span></span>|<span data-ttu-id="d0afd-117">描述</span><span class="sxs-lookup"><span data-stu-id="d0afd-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0afd-118">activityName</span><span class="sxs-lookup"><span data-stu-id="d0afd-118">activityName</span></span>|<span data-ttu-id="d0afd-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d0afd-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="d0afd-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="d0afd-120">childActivityName</span></span>|<span data-ttu-id="d0afd-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d0afd-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0afd-122">子元素</span><span class="sxs-lookup"><span data-stu-id="d0afd-122">Child Elements</span></span>  
 <span data-ttu-id="d0afd-123">无。</span><span class="sxs-lookup"><span data-stu-id="d0afd-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0afd-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d0afd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d0afd-125">元素</span><span class="sxs-lookup"><span data-stu-id="d0afd-125">Element</span></span>|<span data-ttu-id="d0afd-126">描述</span><span class="sxs-lookup"><span data-stu-id="d0afd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0afd-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="d0afd-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="d0afd-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="d0afd-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d0afd-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="d0afd-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0afd-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0afd-130">See Also</span></span>  
 <span data-ttu-id="d0afd-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d0afd-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="d0afd-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d0afd-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="d0afd-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="d0afd-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d0afd-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d0afd-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
