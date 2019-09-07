---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: bc0cc5fd027da45994269b149b72496fa03becef
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398733"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="b48a0-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b48a0-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="b48a0-102">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="b48a0-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b48a0-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="b48a0-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="b48a0-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="b48a0-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b48a0-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="b48a0-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="b48a0-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b48a0-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b48a0-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b48a0-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b48a0-108">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b48a0-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="b48a0-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="b48a0-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="b48a0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="b48a0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="b48a0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="b48a0-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="b48a0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQueries >**</span><span class="sxs-lookup"><span data-stu-id="b48a0-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="b48a0-113">语法</span><span class="sxs-lookup"><span data-stu-id="b48a0-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b48a0-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b48a0-114">Attributes and Elements</span></span>  
 <span data-ttu-id="b48a0-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b48a0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b48a0-116">特性</span><span class="sxs-lookup"><span data-stu-id="b48a0-116">Attributes</span></span>  
 <span data-ttu-id="b48a0-117">无。</span><span class="sxs-lookup"><span data-stu-id="b48a0-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b48a0-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b48a0-118">Child Elements</span></span>  
  
|<span data-ttu-id="b48a0-119">元素</span><span class="sxs-lookup"><span data-stu-id="b48a0-119">Element</span></span>|<span data-ttu-id="b48a0-120">描述</span><span class="sxs-lookup"><span data-stu-id="b48a0-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b48a0-121">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b48a0-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="b48a0-122">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="b48a0-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b48a0-123">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="b48a0-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b48a0-124">父元素</span><span class="sxs-lookup"><span data-stu-id="b48a0-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b48a0-125">元素</span><span class="sxs-lookup"><span data-stu-id="b48a0-125">Element</span></span>|<span data-ttu-id="b48a0-126">描述</span><span class="sxs-lookup"><span data-stu-id="b48a0-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b48a0-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b48a0-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="b48a0-128">一个配置元素，该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="b48a0-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b48a0-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="b48a0-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b48a0-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b48a0-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b48a0-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b48a0-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
