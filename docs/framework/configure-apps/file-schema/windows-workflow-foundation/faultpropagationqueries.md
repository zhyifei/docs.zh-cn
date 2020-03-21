---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 3d6d03638ec5806448a16cc32b37e630d6198624
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152126"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="9c69b-101">\<故障传播查询></span><span class="sxs-lookup"><span data-stu-id="9c69b-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="9c69b-102">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="9c69b-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9c69b-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="9c69b-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="9c69b-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="9c69b-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="9c69b-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="9c69b-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="9c69b-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="9c69b-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="9c69b-107">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9c69b-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9c69b-108">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9c69b-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="9c69b-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="9c69b-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="9c69b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪配置文件>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="9c69b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="9c69b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="9c69b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="9c69b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<故障传播查询>**</span><span class="sxs-lookup"><span data-stu-id="9c69b-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="9c69b-113">语法</span><span class="sxs-lookup"><span data-stu-id="9c69b-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c69b-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9c69b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="9c69b-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9c69b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c69b-116">属性</span><span class="sxs-lookup"><span data-stu-id="9c69b-116">Attributes</span></span>  
 <span data-ttu-id="9c69b-117">无。</span><span class="sxs-lookup"><span data-stu-id="9c69b-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9c69b-118">子元素</span><span class="sxs-lookup"><span data-stu-id="9c69b-118">Child Elements</span></span>  
  
|<span data-ttu-id="9c69b-119">元素</span><span class="sxs-lookup"><span data-stu-id="9c69b-119">Element</span></span>|<span data-ttu-id="9c69b-120">说明</span><span class="sxs-lookup"><span data-stu-id="9c69b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c69b-121">\<故障传播查询></span><span class="sxs-lookup"><span data-stu-id="9c69b-121">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="9c69b-122">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="9c69b-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="9c69b-123">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="9c69b-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9c69b-124">父元素</span><span class="sxs-lookup"><span data-stu-id="9c69b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9c69b-125">元素</span><span class="sxs-lookup"><span data-stu-id="9c69b-125">Element</span></span>|<span data-ttu-id="9c69b-126">说明</span><span class="sxs-lookup"><span data-stu-id="9c69b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c69b-127">\<工作流></span><span class="sxs-lookup"><span data-stu-id="9c69b-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="9c69b-128">包含**活动定义 Id**属性标识的特定工作流的所有查询的配置元素。</span><span class="sxs-lookup"><span data-stu-id="9c69b-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9c69b-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c69b-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9c69b-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9c69b-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9c69b-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9c69b-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
