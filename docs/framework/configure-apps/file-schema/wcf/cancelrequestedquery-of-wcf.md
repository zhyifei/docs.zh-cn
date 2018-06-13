---
title: WCF 的 &lt;cancelRequestedQuery&gt;
ms.date: 03/30/2017
ms.assetid: b690d870-02eb-4c56-8bc3-e5ca99d7097b
ms.openlocfilehash: 41964561a460babc41de755e213971593047b707
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748511"
---
# <a name="ltcancelrequestedquerygt-of-wcf"></a><span data-ttu-id="0f664-102">WCF 的 &lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="0f664-102">&lt;cancelRequestedQuery&gt; of WCF</span></span>
<span data-ttu-id="0f664-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="0f664-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0f664-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="0f664-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0f664-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="0f664-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="0f664-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="0f664-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0f664-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="0f664-107">\<tracking></span></span>  
<span data-ttu-id="0f664-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0f664-108">\<trackingProfile></span></span>  
<span data-ttu-id="0f664-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="0f664-109">\<workflow></span></span>  
<span data-ttu-id="0f664-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="0f664-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="0f664-111">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="0f664-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f664-112">语法</span><span class="sxs-lookup"><span data-stu-id="0f664-112">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0f664-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0f664-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0f664-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0f664-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0f664-115">特性</span><span class="sxs-lookup"><span data-stu-id="0f664-115">Attributes</span></span>  
  
|<span data-ttu-id="0f664-116">特性</span><span class="sxs-lookup"><span data-stu-id="0f664-116">Attribute</span></span>|<span data-ttu-id="0f664-117">描述</span><span class="sxs-lookup"><span data-stu-id="0f664-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f664-118">activityName</span><span class="sxs-lookup"><span data-stu-id="0f664-118">activityName</span></span>|<span data-ttu-id="0f664-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="0f664-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="0f664-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="0f664-120">childActivityName</span></span>|<span data-ttu-id="0f664-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="0f664-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0f664-122">子元素</span><span class="sxs-lookup"><span data-stu-id="0f664-122">Child Elements</span></span>  
 <span data-ttu-id="0f664-123">无。</span><span class="sxs-lookup"><span data-stu-id="0f664-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0f664-124">父元素</span><span class="sxs-lookup"><span data-stu-id="0f664-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0f664-125">元素</span><span class="sxs-lookup"><span data-stu-id="0f664-125">Element</span></span>|<span data-ttu-id="0f664-126">描述</span><span class="sxs-lookup"><span data-stu-id="0f664-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0f664-127">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="0f664-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="0f664-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="0f664-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0f664-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="0f664-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0f664-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f664-130">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>     
 [<span data-ttu-id="0f664-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="0f664-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0f664-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="0f664-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
