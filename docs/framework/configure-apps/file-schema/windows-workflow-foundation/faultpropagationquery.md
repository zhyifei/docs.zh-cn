---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 6b43a570b4d4534adce1ef5ab394849651e3ac0e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398721"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="63620-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="63620-101">\<faultPropagationQuery></span></span>

<span data-ttu-id="63620-102">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="63620-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="63620-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="63620-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="63620-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="63620-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="63620-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="63620-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

 <span data-ttu-id="63620-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="63620-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="63620-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="63620-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="63620-108">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="63620-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="63620-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="63620-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="63620-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="63620-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="63620-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="63620-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="63620-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<faultPropagationQueries >** ](faultpropagationqueries.md)</span><span class="sxs-lookup"><span data-stu-id="63620-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)</span></span>\
<span data-ttu-id="63620-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="63620-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>

## <a name="syntax"></a><span data-ttu-id="63620-114">语法</span><span class="sxs-lookup"><span data-stu-id="63620-114">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="63620-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="63620-115">Attributes and Elements</span></span>

<span data-ttu-id="63620-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="63620-116">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="63620-117">特性</span><span class="sxs-lookup"><span data-stu-id="63620-117">Attributes</span></span>

|<span data-ttu-id="63620-118">特性</span><span class="sxs-lookup"><span data-stu-id="63620-118">Attribute</span></span>|<span data-ttu-id="63620-119">描述</span><span class="sxs-lookup"><span data-stu-id="63620-119">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="63620-120">activityName</span><span class="sxs-lookup"><span data-stu-id="63620-120">activityName</span></span>|<span data-ttu-id="63620-121">一个字符串，指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="63620-121">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="63620-122">默认值为 \*，指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="63620-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|<span data-ttu-id="63620-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="63620-123">faultHandlerActivityName</span></span>|<span data-ttu-id="63620-124">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="63620-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="63620-125">子元素</span><span class="sxs-lookup"><span data-stu-id="63620-125">Child Elements</span></span>

<span data-ttu-id="63620-126">无。</span><span class="sxs-lookup"><span data-stu-id="63620-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="63620-127">父元素</span><span class="sxs-lookup"><span data-stu-id="63620-127">Parent Elements</span></span>

|<span data-ttu-id="63620-128">元素</span><span class="sxs-lookup"><span data-stu-id="63620-128">Element</span></span>|<span data-ttu-id="63620-129">描述</span><span class="sxs-lookup"><span data-stu-id="63620-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="63620-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="63620-130">\<faultPropagationQueries></span></span>](faultpropagationqueries.md)|<span data-ttu-id="63620-131">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="63620-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="63620-132">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="63620-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="63620-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="63620-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="63620-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="63620-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="63620-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="63620-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
