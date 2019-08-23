---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: f77a613f4eb0456a0085096aa478d37c78122217
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946304"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="b68ad-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b68ad-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="b68ad-102">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="b68ad-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b68ad-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="b68ad-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="b68ad-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="b68ad-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b68ad-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="b68ad-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="b68ad-106">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b68ad-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="b68ad-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b68ad-107">\<system.serviceModel></span></span>\
<span data-ttu-id="b68ad-108">\<跟踪 > </span><span class="sxs-lookup"><span data-stu-id="b68ad-108">\<tracking></span></span>\
<span data-ttu-id="b68ad-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b68ad-109">\<trackingProfile></span></span>\
<span data-ttu-id="b68ad-110">\<工作流 > </span><span class="sxs-lookup"><span data-stu-id="b68ad-110">\<workflow></span></span>\
<span data-ttu-id="b68ad-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b68ad-111">\<faultPropagationQueries></span></span>\
<span data-ttu-id="b68ad-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b68ad-112">\<faultPropagationQuery></span></span>

## <a name="syntax"></a><span data-ttu-id="b68ad-113">语法</span><span class="sxs-lookup"><span data-stu-id="b68ad-113">Syntax</span></span>

```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b68ad-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b68ad-114">Attributes and Elements</span></span>

<span data-ttu-id="b68ad-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b68ad-115">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b68ad-116">特性</span><span class="sxs-lookup"><span data-stu-id="b68ad-116">Attributes</span></span>

|<span data-ttu-id="b68ad-117">特性</span><span class="sxs-lookup"><span data-stu-id="b68ad-117">Attribute</span></span>|<span data-ttu-id="b68ad-118">描述</span><span class="sxs-lookup"><span data-stu-id="b68ad-118">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="b68ad-119">activityName</span><span class="sxs-lookup"><span data-stu-id="b68ad-119">activityName</span></span>|<span data-ttu-id="b68ad-120">一个字符串, 指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="b68ad-120">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="b68ad-121">默认值为 \*，指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="b68ad-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="b68ad-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="b68ad-122">faultHandlerActivityName</span></span>|<span data-ttu-id="b68ad-123">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="b68ad-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="b68ad-124">子元素</span><span class="sxs-lookup"><span data-stu-id="b68ad-124">Child Elements</span></span>

<span data-ttu-id="b68ad-125">无。</span><span class="sxs-lookup"><span data-stu-id="b68ad-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="b68ad-126">父元素</span><span class="sxs-lookup"><span data-stu-id="b68ad-126">Parent Elements</span></span>

|<span data-ttu-id="b68ad-127">元素</span><span class="sxs-lookup"><span data-stu-id="b68ad-127">Element</span></span>|<span data-ttu-id="b68ad-128">描述</span><span class="sxs-lookup"><span data-stu-id="b68ad-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b68ad-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b68ad-129">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="b68ad-130">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="b68ad-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b68ad-131">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="b68ad-131">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="b68ad-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b68ad-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b68ad-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b68ad-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b68ad-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b68ad-134">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
