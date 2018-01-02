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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84c9635b37c592b4d82635deb58880d81d2fb5cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="e84ab-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="e84ab-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="e84ab-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e84ab-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e84ab-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="e84ab-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e84ab-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e84ab-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e84ab-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e84ab-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e84ab-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e84ab-107">\<tracking></span></span>  
<span data-ttu-id="e84ab-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e84ab-108">\<trackingProfile></span></span>  
<span data-ttu-id="e84ab-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e84ab-109">\<workflow></span></span>  
<span data-ttu-id="e84ab-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="e84ab-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e84ab-111">语法</span><span class="sxs-lookup"><span data-stu-id="e84ab-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e84ab-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e84ab-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e84ab-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e84ab-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e84ab-114">特性</span><span class="sxs-lookup"><span data-stu-id="e84ab-114">Attributes</span></span>  
 <span data-ttu-id="e84ab-115">无。</span><span class="sxs-lookup"><span data-stu-id="e84ab-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e84ab-116">子元素</span><span class="sxs-lookup"><span data-stu-id="e84ab-116">Child Elements</span></span>  
  
|<span data-ttu-id="e84ab-117">元素</span><span class="sxs-lookup"><span data-stu-id="e84ab-117">Element</span></span>|<span data-ttu-id="e84ab-118">描述</span><span class="sxs-lookup"><span data-stu-id="e84ab-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e84ab-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e84ab-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="e84ab-120">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e84ab-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e84ab-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e84ab-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e84ab-122">元素</span><span class="sxs-lookup"><span data-stu-id="e84ab-122">Element</span></span>|<span data-ttu-id="e84ab-123">描述</span><span class="sxs-lookup"><span data-stu-id="e84ab-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e84ab-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e84ab-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e84ab-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="e84ab-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e84ab-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="e84ab-126">See Also</span></span>  
 <span data-ttu-id="e84ab-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e84ab-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="e84ab-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="e84ab-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="e84ab-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e84ab-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e84ab-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e84ab-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
