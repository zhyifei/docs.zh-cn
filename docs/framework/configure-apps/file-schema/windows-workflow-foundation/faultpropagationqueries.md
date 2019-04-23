---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 402b938913575adfa9125b981dc2913680f07b73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204037"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="1259d-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1259d-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="1259d-102">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="1259d-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1259d-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1259d-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1259d-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="1259d-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1259d-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="1259d-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="1259d-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="1259d-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1259d-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1259d-107">\<system.serviceModel></span></span>  
<span data-ttu-id="1259d-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="1259d-108">\<tracking></span></span>  
<span data-ttu-id="1259d-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1259d-109">\<trackingProfile></span></span>  
<span data-ttu-id="1259d-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1259d-110">\<workflow></span></span>  
<span data-ttu-id="1259d-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1259d-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1259d-112">语法</span><span class="sxs-lookup"><span data-stu-id="1259d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1259d-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1259d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1259d-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1259d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1259d-115">特性</span><span class="sxs-lookup"><span data-stu-id="1259d-115">Attributes</span></span>  
 <span data-ttu-id="1259d-116">无。</span><span class="sxs-lookup"><span data-stu-id="1259d-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1259d-117">子元素</span><span class="sxs-lookup"><span data-stu-id="1259d-117">Child Elements</span></span>  
  
|<span data-ttu-id="1259d-118">元素</span><span class="sxs-lookup"><span data-stu-id="1259d-118">Element</span></span>|<span data-ttu-id="1259d-119">描述</span><span class="sxs-lookup"><span data-stu-id="1259d-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1259d-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="1259d-120">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="1259d-121">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="1259d-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1259d-122">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1259d-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1259d-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1259d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1259d-124">元素</span><span class="sxs-lookup"><span data-stu-id="1259d-124">Element</span></span>|<span data-ttu-id="1259d-125">描述</span><span class="sxs-lookup"><span data-stu-id="1259d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1259d-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1259d-126">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="1259d-127">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="1259d-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1259d-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1259d-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1259d-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1259d-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1259d-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1259d-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
