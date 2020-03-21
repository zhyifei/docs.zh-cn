---
title: <cancelRequestedQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 8da9b1c4-338a-4f23-9830-6d257772d340
ms.openlocfilehash: 3e6840ce647625c36356cccd4651f17de32777e2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152282"
---
# <a name="cancelrequestedquery"></a><span data-ttu-id="7a681-101">\<取消请求查询></span><span class="sxs-lookup"><span data-stu-id="7a681-101">\<cancelRequestedQuery></span></span>
<span data-ttu-id="7a681-102">表示一个查询，该查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="7a681-102">Represents a query that is used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7a681-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="7a681-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="7a681-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="7a681-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="7a681-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a681-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a681-106">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7a681-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="7a681-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="7a681-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="7a681-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪配置文件>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="7a681-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="7a681-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="7a681-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="7a681-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<取消请求查询>**](cancelrequestedqueries.md)</span><span class="sxs-lookup"><span data-stu-id="7a681-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cancelRequestedQueries>**](cancelrequestedqueries.md)</span></span>\
<span data-ttu-id="7a681-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<取消请求查询>**</span><span class="sxs-lookup"><span data-stu-id="7a681-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a681-112">语法</span><span class="sxs-lookup"><span data-stu-id="7a681-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a681-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7a681-113">Attributes and Elements</span></span>  
 <span data-ttu-id="7a681-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7a681-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a681-115">属性</span><span class="sxs-lookup"><span data-stu-id="7a681-115">Attributes</span></span>  
  
|<span data-ttu-id="7a681-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="7a681-116">Attribute</span></span>|<span data-ttu-id="7a681-117">说明</span><span class="sxs-lookup"><span data-stu-id="7a681-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7a681-118">activityName</span><span class="sxs-lookup"><span data-stu-id="7a681-118">activityName</span></span>|<span data-ttu-id="7a681-119">一个字符串，指定正在请求取消的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7a681-119">A string that specifies the name of the activity that is requesting the cancellation.</span></span>|  
|<span data-ttu-id="7a681-120">childActivityName</span><span class="sxs-lookup"><span data-stu-id="7a681-120">childActivityName</span></span>|<span data-ttu-id="7a681-121">一个字符串，指定已请求将其取消的子活动的名称。</span><span class="sxs-lookup"><span data-stu-id="7a681-121">A string that specifies the name of the child activity for which cancellation was requested.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a681-122">子元素</span><span class="sxs-lookup"><span data-stu-id="7a681-122">Child Elements</span></span>  
 <span data-ttu-id="7a681-123">无。</span><span class="sxs-lookup"><span data-stu-id="7a681-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a681-124">父元素</span><span class="sxs-lookup"><span data-stu-id="7a681-124">Parent Elements</span></span>  
  
|<span data-ttu-id="7a681-125">元素</span><span class="sxs-lookup"><span data-stu-id="7a681-125">Element</span></span>|<span data-ttu-id="7a681-126">说明</span><span class="sxs-lookup"><span data-stu-id="7a681-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a681-127">\<故障传播查询></span><span class="sxs-lookup"><span data-stu-id="7a681-127">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="7a681-128">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="7a681-128">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="7a681-129">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="7a681-129">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a681-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a681-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CancelRequestedQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CancelRequestedQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7a681-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7a681-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7a681-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7a681-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
