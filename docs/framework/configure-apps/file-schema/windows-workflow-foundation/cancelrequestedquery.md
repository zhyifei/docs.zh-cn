---
title: '&lt;cancelRequestedQuery&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: a3d24536589288ce9585901f3d955075bc856c97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520303"
---
# <a name="ltcancelrequestedquerygt"></a><span data-ttu-id="02f9e-102">&lt;cancelRequestedQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="02f9e-102">&lt;cancelRequestedQuery&gt;</span></span>
<span data-ttu-id="02f9e-103">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="02f9e-103">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="02f9e-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="02f9e-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="02f9e-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="02f9e-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="02f9e-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="02f9e-106">\<system.serviceModel></span></span>  
<span data-ttu-id="02f9e-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="02f9e-107">\<tracking></span></span>  
<span data-ttu-id="02f9e-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="02f9e-108">\<trackingProfile></span></span>  
<span data-ttu-id="02f9e-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="02f9e-109">\<workflow></span></span>  
<span data-ttu-id="02f9e-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="02f9e-110">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="02f9e-111">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="02f9e-111">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02f9e-112">语法</span><span class="sxs-lookup"><span data-stu-id="02f9e-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02f9e-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="02f9e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="02f9e-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="02f9e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02f9e-115">特性</span><span class="sxs-lookup"><span data-stu-id="02f9e-115">Attributes</span></span>  
  
|<span data-ttu-id="02f9e-116">特性</span><span class="sxs-lookup"><span data-stu-id="02f9e-116">Attribute</span></span>|<span data-ttu-id="02f9e-117">描述</span><span class="sxs-lookup"><span data-stu-id="02f9e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02f9e-118">activityName</span><span class="sxs-lookup"><span data-stu-id="02f9e-118">activityName</span></span>|<span data-ttu-id="02f9e-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="02f9e-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="02f9e-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="02f9e-120">childActivityName</span></span>|<span data-ttu-id="02f9e-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="02f9e-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02f9e-122">子元素</span><span class="sxs-lookup"><span data-stu-id="02f9e-122">Child Elements</span></span>  
 <span data-ttu-id="02f9e-123">无。</span><span class="sxs-lookup"><span data-stu-id="02f9e-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="02f9e-124">父元素</span><span class="sxs-lookup"><span data-stu-id="02f9e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="02f9e-125">元素</span><span class="sxs-lookup"><span data-stu-id="02f9e-125">Element</span></span>|<span data-ttu-id="02f9e-126">描述</span><span class="sxs-lookup"><span data-stu-id="02f9e-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02f9e-127">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="02f9e-127">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="02f9e-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="02f9e-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="02f9e-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="02f9e-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="02f9e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="02f9e-130">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="02f9e-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="02f9e-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="02f9e-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="02f9e-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
