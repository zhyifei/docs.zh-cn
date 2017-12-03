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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6fc9df52c691e13802607714977f3aa778cde84e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="7a236-102">WCF 的 &lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="7a236-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="7a236-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="7a236-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7a236-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="7a236-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="7a236-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="7a236-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="7a236-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="7a236-106">\<system.serviceModel></span></span>  
<span data-ttu-id="7a236-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7a236-107">\<tracking></span></span>  
<span data-ttu-id="7a236-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="7a236-108">\<trackingProfile></span></span>  
<span data-ttu-id="7a236-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="7a236-109">\<workflow></span></span>  
<span data-ttu-id="7a236-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="7a236-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="7a236-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="7a236-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a236-112">语法</span><span class="sxs-lookup"><span data-stu-id="7a236-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7a236-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7a236-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7a236-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7a236-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a236-115">特性</span><span class="sxs-lookup"><span data-stu-id="7a236-115">Attributes</span></span>  
  
|<span data-ttu-id="7a236-116">特性</span><span class="sxs-lookup"><span data-stu-id="7a236-116">Attribute</span></span>|<span data-ttu-id="7a236-117">描述</span><span class="sxs-lookup"><span data-stu-id="7a236-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a236-118">activityName</span><span class="sxs-lookup"><span data-stu-id="7a236-118">activityName</span></span>|<span data-ttu-id="7a236-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7a236-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="7a236-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="7a236-120">childActivityName</span></span>|<span data-ttu-id="7a236-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7a236-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a236-122">子元素</span><span class="sxs-lookup"><span data-stu-id="7a236-122">Child Elements</span></span>  
 <span data-ttu-id="7a236-123">无。</span><span class="sxs-lookup"><span data-stu-id="7a236-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a236-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7a236-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7a236-125">元素</span><span class="sxs-lookup"><span data-stu-id="7a236-125">Element</span></span>|<span data-ttu-id="7a236-126">描述</span><span class="sxs-lookup"><span data-stu-id="7a236-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a236-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="7a236-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="7a236-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="7a236-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7a236-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="7a236-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a236-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a236-130">See Also</span></span>  
 <span data-ttu-id="7a236-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a236-131"><xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="7a236-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a236-132"><xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType></span></span>     
 [<span data-ttu-id="7a236-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7a236-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="7a236-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7a236-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
