---
title: <faultPropagationQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: a6ef4e198caec4a1f21cedf2ff46d390aeaa2d3b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855327"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="eae71-102">\<WCF 的 y ></span><span class="sxs-lookup"><span data-stu-id="eae71-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="eae71-103">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="eae71-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="eae71-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="eae71-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="eae71-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="eae71-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="eae71-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="eae71-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>

<span data-ttu-id="eae71-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="eae71-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="eae71-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eae71-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eae71-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="eae71-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="eae71-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="eae71-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="eae71-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="eae71-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<faultPropagationQueries >** ](faultpropagationqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eae71-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries-of-wcf.md)</span></span>\
<span data-ttu-id="eae71-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<y >**</span><span class="sxs-lookup"><span data-stu-id="eae71-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="eae71-116">语法</span><span class="sxs-lookup"><span data-stu-id="eae71-116">Syntax</span></span>

```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="eae71-117">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eae71-117">Attributes and elements</span></span>

<span data-ttu-id="eae71-118">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eae71-118">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="eae71-119">特性</span><span class="sxs-lookup"><span data-stu-id="eae71-119">Attributes</span></span>

|<span data-ttu-id="eae71-120">特性</span><span class="sxs-lookup"><span data-stu-id="eae71-120">Attribute</span></span>|<span data-ttu-id="eae71-121">描述</span><span class="sxs-lookup"><span data-stu-id="eae71-121">Description</span></span>|
|---------------|-----------------|
|`faultSourceActivityName`|<span data-ttu-id="eae71-122">一个字符串，指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="eae71-122">A string that specifies the name of the fault handler activity that propagated the fault.</span></span> <span data-ttu-id="eae71-123">默认值为\*，指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="eae71-123">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|
|`faultHandlerActivityName`|<span data-ttu-id="eae71-124">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="eae71-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="eae71-125">子元素</span><span class="sxs-lookup"><span data-stu-id="eae71-125">Child elements</span></span>

<span data-ttu-id="eae71-126">无。</span><span class="sxs-lookup"><span data-stu-id="eae71-126">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eae71-127">父元素</span><span class="sxs-lookup"><span data-stu-id="eae71-127">Parent elements</span></span>

|<span data-ttu-id="eae71-128">元素</span><span class="sxs-lookup"><span data-stu-id="eae71-128">Element</span></span>|<span data-ttu-id="eae71-129">描述</span><span class="sxs-lookup"><span data-stu-id="eae71-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="eae71-130">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="eae71-130">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="eae71-131">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="eae71-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="eae71-132">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="eae71-132">This event occurs each time a FaultHandler processes a fault.</span></span>|

## <a name="see-also"></a><span data-ttu-id="eae71-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="eae71-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eae71-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="eae71-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eae71-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="eae71-135">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
