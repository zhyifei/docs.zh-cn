---
title: '&lt;faultPropagationQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 00ff90ae-ebe0-4c85-a93f-61557288d0a3
ms.openlocfilehash: 5fd6ffc9560247089c7fbb60b0e5a7d3a417ea6f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755144"
---
# <a name="ltfaultpropagationqueriesgt"></a><span data-ttu-id="53133-102">&lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="53133-102">&lt;faultPropagationQueries&gt;</span></span>
<span data-ttu-id="53133-103">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="53133-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="53133-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="53133-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="53133-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="53133-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="53133-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="53133-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="53133-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="53133-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="53133-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="53133-108">\<system.serviceModel></span></span>  
<span data-ttu-id="53133-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="53133-109">\<tracking></span></span>  
<span data-ttu-id="53133-110">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="53133-110">\<trackingProfile></span></span>  
<span data-ttu-id="53133-111">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="53133-111">\<workflow></span></span>  
<span data-ttu-id="53133-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="53133-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53133-113">语法</span><span class="sxs-lookup"><span data-stu-id="53133-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53133-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53133-114">Attributes and Elements</span></span>  
 <span data-ttu-id="53133-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="53133-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53133-116">特性</span><span class="sxs-lookup"><span data-stu-id="53133-116">Attributes</span></span>  
 <span data-ttu-id="53133-117">无。</span><span class="sxs-lookup"><span data-stu-id="53133-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53133-118">子元素</span><span class="sxs-lookup"><span data-stu-id="53133-118">Child Elements</span></span>  
  
|<span data-ttu-id="53133-119">元素</span><span class="sxs-lookup"><span data-stu-id="53133-119">Element</span></span>|<span data-ttu-id="53133-120">描述</span><span class="sxs-lookup"><span data-stu-id="53133-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53133-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="53133-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="53133-122">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="53133-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="53133-123">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="53133-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53133-124">父元素</span><span class="sxs-lookup"><span data-stu-id="53133-124">Parent Elements</span></span>  
  
|<span data-ttu-id="53133-125">元素</span><span class="sxs-lookup"><span data-stu-id="53133-125">Element</span></span>|<span data-ttu-id="53133-126">描述</span><span class="sxs-lookup"><span data-stu-id="53133-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53133-127">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="53133-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="53133-128">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="53133-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="53133-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="53133-129">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="53133-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="53133-130">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="53133-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="53133-131">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
