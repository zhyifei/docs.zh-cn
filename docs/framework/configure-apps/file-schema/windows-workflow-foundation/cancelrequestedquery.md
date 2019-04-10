---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215308"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="d1daa-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d1daa-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="d1daa-102">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="d1daa-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d1daa-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="d1daa-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d1daa-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="d1daa-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="d1daa-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d1daa-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d1daa-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d1daa-106">\<tracking></span></span>  
<span data-ttu-id="d1daa-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d1daa-107">\<trackingProfile></span></span>  
<span data-ttu-id="d1daa-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d1daa-108">\<workflow></span></span>  
<span data-ttu-id="d1daa-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d1daa-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="d1daa-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d1daa-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1daa-111">语法</span><span class="sxs-lookup"><span data-stu-id="d1daa-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d1daa-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d1daa-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d1daa-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d1daa-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d1daa-114">特性</span><span class="sxs-lookup"><span data-stu-id="d1daa-114">Attributes</span></span>  
  
|<span data-ttu-id="d1daa-115">特性</span><span class="sxs-lookup"><span data-stu-id="d1daa-115">Attribute</span></span>|<span data-ttu-id="d1daa-116">描述</span><span class="sxs-lookup"><span data-stu-id="d1daa-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d1daa-117">activityName</span><span class="sxs-lookup"><span data-stu-id="d1daa-117">activityName</span></span>|<span data-ttu-id="d1daa-118">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d1daa-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="d1daa-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="d1daa-119">childActivityName</span></span>|<span data-ttu-id="d1daa-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d1daa-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d1daa-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d1daa-121">Child Elements</span></span>  
 <span data-ttu-id="d1daa-122">无。</span><span class="sxs-lookup"><span data-stu-id="d1daa-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d1daa-123">父元素</span><span class="sxs-lookup"><span data-stu-id="d1daa-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d1daa-124">元素</span><span class="sxs-lookup"><span data-stu-id="d1daa-124">Element</span></span>|<span data-ttu-id="d1daa-125">描述</span><span class="sxs-lookup"><span data-stu-id="d1daa-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d1daa-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="d1daa-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="d1daa-127">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="d1daa-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d1daa-128">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="d1daa-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d1daa-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1daa-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d1daa-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="d1daa-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d1daa-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d1daa-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
