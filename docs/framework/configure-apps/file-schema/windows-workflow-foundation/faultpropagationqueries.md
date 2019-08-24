---
title: <faultPropagationQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: b8052138a729fcba7cb158d81a63126f59e0c4fc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69988734"
---
# <a name="faultpropagationqueries"></a><span data-ttu-id="1e7f1-101">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1e7f1-101">\<faultPropagationQueries></span></span>
<span data-ttu-id="1e7f1-102">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-102">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1e7f1-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1e7f1-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1e7f1-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="1e7f1-106">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1e7f1-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1e7f1-107">\<system.serviceModel></span></span>  
<span data-ttu-id="1e7f1-108">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="1e7f1-108">\<tracking></span></span>  
<span data-ttu-id="1e7f1-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1e7f1-109">\<trackingProfile></span></span>  
<span data-ttu-id="1e7f1-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="1e7f1-110">\<workflow></span></span>  
<span data-ttu-id="1e7f1-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1e7f1-111">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e7f1-112">语法</span><span class="sxs-lookup"><span data-stu-id="1e7f1-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e7f1-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1e7f1-113">Attributes and Elements</span></span>  
 <span data-ttu-id="1e7f1-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e7f1-115">特性</span><span class="sxs-lookup"><span data-stu-id="1e7f1-115">Attributes</span></span>  
 <span data-ttu-id="1e7f1-116">无。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1e7f1-117">子元素</span><span class="sxs-lookup"><span data-stu-id="1e7f1-117">Child Elements</span></span>  
  
|<span data-ttu-id="1e7f1-118">元素</span><span class="sxs-lookup"><span data-stu-id="1e7f1-118">Element</span></span>|<span data-ttu-id="1e7f1-119">描述</span><span class="sxs-lookup"><span data-stu-id="1e7f1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e7f1-120">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="1e7f1-120">\<faultPropagationQuery></span></span>](faultpropagationquery.md)|<span data-ttu-id="1e7f1-121">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1e7f1-122">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e7f1-123">父元素</span><span class="sxs-lookup"><span data-stu-id="1e7f1-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1e7f1-124">元素</span><span class="sxs-lookup"><span data-stu-id="1e7f1-124">Element</span></span>|<span data-ttu-id="1e7f1-125">描述</span><span class="sxs-lookup"><span data-stu-id="1e7f1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e7f1-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="1e7f1-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1e7f1-127">一个配置元素, 该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="1e7f1-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1e7f1-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e7f1-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1e7f1-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1e7f1-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1e7f1-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1e7f1-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
