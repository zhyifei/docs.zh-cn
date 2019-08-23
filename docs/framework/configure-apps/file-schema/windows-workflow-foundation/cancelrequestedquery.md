---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: d9c3f91edb41bd034bcd978b075d62f74b6e308d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945884"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="861ac-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="861ac-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="861ac-102">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="861ac-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="861ac-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="861ac-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="861ac-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="861ac-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="861ac-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="861ac-105">\<system.serviceModel></span></span>  
<span data-ttu-id="861ac-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="861ac-106">\<tracking></span></span>  
<span data-ttu-id="861ac-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="861ac-107">\<trackingProfile></span></span>  
<span data-ttu-id="861ac-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="861ac-108">\<workflow></span></span>  
<span data-ttu-id="861ac-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="861ac-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="861ac-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="861ac-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="861ac-111">语法</span><span class="sxs-lookup"><span data-stu-id="861ac-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="861ac-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="861ac-112">Attributes and Elements</span></span>  
 <span data-ttu-id="861ac-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="861ac-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="861ac-114">特性</span><span class="sxs-lookup"><span data-stu-id="861ac-114">Attributes</span></span>  
  
|<span data-ttu-id="861ac-115">特性</span><span class="sxs-lookup"><span data-stu-id="861ac-115">Attribute</span></span>|<span data-ttu-id="861ac-116">描述</span><span class="sxs-lookup"><span data-stu-id="861ac-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="861ac-117">activityName</span><span class="sxs-lookup"><span data-stu-id="861ac-117">activityName</span></span>|<span data-ttu-id="861ac-118">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="861ac-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="861ac-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="861ac-119">childActivityName</span></span>|<span data-ttu-id="861ac-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="861ac-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="861ac-121">子元素</span><span class="sxs-lookup"><span data-stu-id="861ac-121">Child Elements</span></span>  
 <span data-ttu-id="861ac-122">无。</span><span class="sxs-lookup"><span data-stu-id="861ac-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="861ac-123">父元素</span><span class="sxs-lookup"><span data-stu-id="861ac-123">Parent Elements</span></span>  
  
|<span data-ttu-id="861ac-124">元素</span><span class="sxs-lookup"><span data-stu-id="861ac-124">Element</span></span>|<span data-ttu-id="861ac-125">描述</span><span class="sxs-lookup"><span data-stu-id="861ac-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="861ac-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="861ac-126">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="861ac-127">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="861ac-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="861ac-128">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="861ac-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="861ac-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="861ac-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="861ac-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="861ac-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="861ac-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="861ac-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
