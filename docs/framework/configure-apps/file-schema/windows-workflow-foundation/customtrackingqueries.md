---
title: '&lt;customTrackingQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19a4a58a15db72129f17655e7043f2ee3ae7ffa2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="097fb-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="097fb-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="097fb-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="097fb-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="097fb-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="097fb-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="097fb-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="097fb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="097fb-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="097fb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="097fb-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="097fb-107">\<tracking></span></span>  
<span data-ttu-id="097fb-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="097fb-108">\<trackingProfile></span></span>  
<span data-ttu-id="097fb-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="097fb-109">\<workflow></span></span>  
<span data-ttu-id="097fb-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="097fb-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097fb-111">语法</span><span class="sxs-lookup"><span data-stu-id="097fb-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String" 
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="097fb-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="097fb-112">Attributes and Elements</span></span>  
 <span data-ttu-id="097fb-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="097fb-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="097fb-114">特性</span><span class="sxs-lookup"><span data-stu-id="097fb-114">Attributes</span></span>  
 <span data-ttu-id="097fb-115">无。</span><span class="sxs-lookup"><span data-stu-id="097fb-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="097fb-116">子元素</span><span class="sxs-lookup"><span data-stu-id="097fb-116">Child Elements</span></span>  
  
|<span data-ttu-id="097fb-117">元素</span><span class="sxs-lookup"><span data-stu-id="097fb-117">Element</span></span>|<span data-ttu-id="097fb-118">描述</span><span class="sxs-lookup"><span data-stu-id="097fb-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="097fb-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="097fb-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="097fb-120">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="097fb-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="097fb-121">父元素</span><span class="sxs-lookup"><span data-stu-id="097fb-121">Parent Elements</span></span>  
  
|<span data-ttu-id="097fb-122">元素</span><span class="sxs-lookup"><span data-stu-id="097fb-122">Element</span></span>|<span data-ttu-id="097fb-123">描述</span><span class="sxs-lookup"><span data-stu-id="097fb-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="097fb-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="097fb-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="097fb-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="097fb-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="097fb-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="097fb-126">See Also</span></span>  
 <span data-ttu-id="097fb-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="097fb-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="097fb-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="097fb-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="097fb-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="097fb-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="097fb-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="097fb-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
