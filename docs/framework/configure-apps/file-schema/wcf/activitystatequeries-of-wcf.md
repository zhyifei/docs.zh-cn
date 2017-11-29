---
title: "WCF 的 &lt;activityStateQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fbdd10680da784255a72069a0c1cc240cbe3f15e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="8b5db-102">WCF 的 &lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8b5db-102">&lt;activityStateQueries&gt; of WCF</span></span>
<span data-ttu-id="8b5db-103">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="8b5db-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="8b5db-104">例如，你可能想要跟踪的每次完成工作流实例中的"发送电子邮件"活动。</span><span class="sxs-lookup"><span data-stu-id="8b5db-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="8b5db-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="8b5db-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="8b5db-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="8b5db-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="8b5db-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="8b5db-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="8b5db-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8b5db-108">\<system.serviceModel></span></span>  
<span data-ttu-id="8b5db-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="8b5db-109">\<tracking></span></span>  
<span data-ttu-id="8b5db-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8b5db-110">\<trackingProfile></span></span>  
<span data-ttu-id="8b5db-111">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="8b5db-111">\<workflow></span></span>  
<span data-ttu-id="8b5db-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="8b5db-112">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b5db-113">语法</span><span class="sxs-lookup"><span data-stu-id="8b5db-113">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8b5db-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8b5db-114">Attributes and Elements</span></span>  
 <span data-ttu-id="8b5db-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8b5db-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8b5db-116">特性</span><span class="sxs-lookup"><span data-stu-id="8b5db-116">Attributes</span></span>  
 <span data-ttu-id="8b5db-117">无。</span><span class="sxs-lookup"><span data-stu-id="8b5db-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8b5db-118">子元素</span><span class="sxs-lookup"><span data-stu-id="8b5db-118">Child Elements</span></span>  
  
|<span data-ttu-id="8b5db-119">元素</span><span class="sxs-lookup"><span data-stu-id="8b5db-119">Element</span></span>|<span data-ttu-id="8b5db-120">描述</span><span class="sxs-lookup"><span data-stu-id="8b5db-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b5db-121">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8b5db-121">\<activityStateQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)|<span data-ttu-id="8b5db-122">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="8b5db-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8b5db-123">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="8b5db-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8b5db-124">父元素</span><span class="sxs-lookup"><span data-stu-id="8b5db-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8b5db-125">元素</span><span class="sxs-lookup"><span data-stu-id="8b5db-125">Element</span></span>|<span data-ttu-id="8b5db-126">描述</span><span class="sxs-lookup"><span data-stu-id="8b5db-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8b5db-127">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="8b5db-127">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8b5db-128">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="8b5db-128">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b5db-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b5db-129">See Also</span></span>  
 <span data-ttu-id="8b5db-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection></span><span class="sxs-lookup"><span data-stu-id="8b5db-130"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection></span></span>    
 <span data-ttu-id="8b5db-131"><xref:System.Activities.Tracking.ActivityStateQuery></span><span class="sxs-lookup"><span data-stu-id="8b5db-131"><xref:System.Activities.Tracking.ActivityStateQuery></span></span>    
 [<span data-ttu-id="8b5db-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8b5db-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8b5db-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8b5db-133">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
