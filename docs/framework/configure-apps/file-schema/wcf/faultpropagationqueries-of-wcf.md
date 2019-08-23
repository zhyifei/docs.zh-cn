---
title: <faultPropagationQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: aeb964fc8c96c8cb9aeb316bb95f9565fc4a7f18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918945"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="b0c52-102">\<WCF 的 faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="b0c52-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="b0c52-103">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="b0c52-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b0c52-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="b0c52-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="b0c52-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="b0c52-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="b0c52-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="b0c52-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="b0c52-107">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b0c52-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b0c52-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b0c52-108">\<system.serviceModel></span></span>  
<span data-ttu-id="b0c52-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="b0c52-109">\<tracking></span></span>  
<span data-ttu-id="b0c52-110">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="b0c52-110">\<profiles></span></span>  
<span data-ttu-id="b0c52-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b0c52-111">\<trackingProfile></span></span>  
<span data-ttu-id="b0c52-112">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="b0c52-112">\<workflow></span></span>  
<span data-ttu-id="b0c52-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="b0c52-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c52-114">语法</span><span class="sxs-lookup"><span data-stu-id="b0c52-114">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0c52-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b0c52-115">Attributes and elements</span></span>

<span data-ttu-id="b0c52-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b0c52-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="b0c52-117">特性</span><span class="sxs-lookup"><span data-stu-id="b0c52-117">Attributes</span></span>

<span data-ttu-id="b0c52-118">无。</span><span class="sxs-lookup"><span data-stu-id="b0c52-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b0c52-119">子元素</span><span class="sxs-lookup"><span data-stu-id="b0c52-119">Child elements</span></span>

|<span data-ttu-id="b0c52-120">元素</span><span class="sxs-lookup"><span data-stu-id="b0c52-120">Element</span></span>|<span data-ttu-id="b0c52-121">描述</span><span class="sxs-lookup"><span data-stu-id="b0c52-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0c52-122">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="b0c52-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="b0c52-123">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="b0c52-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="b0c52-124">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="b0c52-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0c52-125">父元素</span><span class="sxs-lookup"><span data-stu-id="b0c52-125">Parent elements</span></span>  
  
|<span data-ttu-id="b0c52-126">元素</span><span class="sxs-lookup"><span data-stu-id="b0c52-126">Element</span></span>|<span data-ttu-id="b0c52-127">描述</span><span class="sxs-lookup"><span data-stu-id="b0c52-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b0c52-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b0c52-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b0c52-129">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="b0c52-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b0c52-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0c52-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b0c52-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b0c52-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b0c52-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b0c52-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
