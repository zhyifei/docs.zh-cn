---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 5f2e46d5e4cdd64c37219476790b9ff92c606b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790229"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="3dd18-101">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="3dd18-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="3dd18-102">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="3dd18-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3dd18-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="3dd18-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="3dd18-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="3dd18-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3dd18-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3dd18-105">\<system.serviceModel></span></span>  
<span data-ttu-id="3dd18-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="3dd18-106">\<tracking></span></span>  
<span data-ttu-id="3dd18-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="3dd18-107">\<trackingProfile></span></span>  
<span data-ttu-id="3dd18-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="3dd18-108">\<workflow></span></span>  
<span data-ttu-id="3dd18-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="3dd18-109">\<cancelRequestedQueries></span></span>  
<span data-ttu-id="3dd18-110">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="3dd18-110">\<cancelRequestedQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3dd18-111">语法</span><span class="sxs-lookup"><span data-stu-id="3dd18-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3dd18-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3dd18-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3dd18-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3dd18-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3dd18-114">特性</span><span class="sxs-lookup"><span data-stu-id="3dd18-114">Attributes</span></span>  
  
|<span data-ttu-id="3dd18-115">特性</span><span class="sxs-lookup"><span data-stu-id="3dd18-115">Attribute</span></span>|<span data-ttu-id="3dd18-116">描述</span><span class="sxs-lookup"><span data-stu-id="3dd18-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3dd18-117">activityName</span><span class="sxs-lookup"><span data-stu-id="3dd18-117">activityName</span></span>|<span data-ttu-id="3dd18-118">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="3dd18-118">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="3dd18-119">childActivityName</span><span class="sxs-lookup"><span data-stu-id="3dd18-119">childActivityName</span></span>|<span data-ttu-id="3dd18-120">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="3dd18-120">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3dd18-121">子元素</span><span class="sxs-lookup"><span data-stu-id="3dd18-121">Child Elements</span></span>  
 <span data-ttu-id="3dd18-122">无。</span><span class="sxs-lookup"><span data-stu-id="3dd18-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3dd18-123">父元素</span><span class="sxs-lookup"><span data-stu-id="3dd18-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3dd18-124">元素</span><span class="sxs-lookup"><span data-stu-id="3dd18-124">Element</span></span>|<span data-ttu-id="3dd18-125">描述</span><span class="sxs-lookup"><span data-stu-id="3dd18-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3dd18-126">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="3dd18-126">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="3dd18-127">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="3dd18-127">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="3dd18-128">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="3dd18-128">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3dd18-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="3dd18-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="3dd18-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="3dd18-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="3dd18-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="3dd18-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
