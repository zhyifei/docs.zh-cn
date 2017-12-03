---
title: "WCF 的 &lt;faultPropagationQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 771908114f4f4e1cc2588e39e7f3d811c336a05a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="d72d5-102">WCF 的 &lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="d72d5-102">&lt;faultPropagationQueries&gt; of WCF</span></span>
<span data-ttu-id="d72d5-103">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="d72d5-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d72d5-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="d72d5-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="d72d5-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="d72d5-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="d72d5-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="d72d5-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="d72d5-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="d72d5-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="d72d5-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d72d5-108">\<system.serviceModel></span></span>  
<span data-ttu-id="d72d5-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="d72d5-109">\<tracking></span></span>  
<span data-ttu-id="d72d5-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="d72d5-110">\<trackingProfile></span></span>  
<span data-ttu-id="d72d5-111">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="d72d5-111">\<workflow></span></span>  
<span data-ttu-id="d72d5-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="d72d5-112">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d72d5-113">语法</span><span class="sxs-lookup"><span data-stu-id="d72d5-113">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d72d5-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d72d5-114">Attributes and Elements</span></span>  
 <span data-ttu-id="d72d5-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d72d5-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d72d5-116">特性</span><span class="sxs-lookup"><span data-stu-id="d72d5-116">Attributes</span></span>  
 <span data-ttu-id="d72d5-117">无。</span><span class="sxs-lookup"><span data-stu-id="d72d5-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d72d5-118">子元素</span><span class="sxs-lookup"><span data-stu-id="d72d5-118">Child Elements</span></span>  
  
|<span data-ttu-id="d72d5-119">元素</span><span class="sxs-lookup"><span data-stu-id="d72d5-119">Element</span></span>|<span data-ttu-id="d72d5-120">描述</span><span class="sxs-lookup"><span data-stu-id="d72d5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d72d5-121">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="d72d5-121">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="d72d5-122">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="d72d5-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="d72d5-123">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="d72d5-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d72d5-124">父元素</span><span class="sxs-lookup"><span data-stu-id="d72d5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d72d5-125">元素</span><span class="sxs-lookup"><span data-stu-id="d72d5-125">Element</span></span>|<span data-ttu-id="d72d5-126">描述</span><span class="sxs-lookup"><span data-stu-id="d72d5-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d72d5-127">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="d72d5-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d72d5-128">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="d72d5-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d72d5-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d72d5-129">See Also</span></span>  
 <span data-ttu-id="d72d5-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d72d5-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="d72d5-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d72d5-131"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="d72d5-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="d72d5-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="d72d5-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d72d5-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
