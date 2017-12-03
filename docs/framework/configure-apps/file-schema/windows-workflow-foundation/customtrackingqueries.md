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
ms.openlocfilehash: 241684a3a2344d6eb7f3b34c81c581b0ec5130f1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="8e35a-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="8e35a-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="8e35a-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="8e35a-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="8e35a-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="8e35a-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="8e35a-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8e35a-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8e35a-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8e35a-106">\<system.serviceModel></span></span>  
<span data-ttu-id="8e35a-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="8e35a-107">\<tracking></span></span>  
<span data-ttu-id="8e35a-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="8e35a-108">\<trackingProfile></span></span>  
<span data-ttu-id="8e35a-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="8e35a-109">\<workflow></span></span>  
<span data-ttu-id="8e35a-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="8e35a-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e35a-111">语法</span><span class="sxs-lookup"><span data-stu-id="8e35a-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e35a-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8e35a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8e35a-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8e35a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e35a-114">特性</span><span class="sxs-lookup"><span data-stu-id="8e35a-114">Attributes</span></span>  
 <span data-ttu-id="8e35a-115">无。</span><span class="sxs-lookup"><span data-stu-id="8e35a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8e35a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="8e35a-116">Child Elements</span></span>  
  
|<span data-ttu-id="8e35a-117">元素</span><span class="sxs-lookup"><span data-stu-id="8e35a-117">Element</span></span>|<span data-ttu-id="8e35a-118">描述</span><span class="sxs-lookup"><span data-stu-id="8e35a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e35a-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="8e35a-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="8e35a-120">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="8e35a-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8e35a-121">父元素</span><span class="sxs-lookup"><span data-stu-id="8e35a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8e35a-122">元素</span><span class="sxs-lookup"><span data-stu-id="8e35a-122">Element</span></span>|<span data-ttu-id="8e35a-123">描述</span><span class="sxs-lookup"><span data-stu-id="8e35a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e35a-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="8e35a-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="8e35a-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="8e35a-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8e35a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e35a-126">See Also</span></span>  
 <span data-ttu-id="8e35a-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8e35a-127"><xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="8e35a-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="8e35a-128"><xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="8e35a-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8e35a-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8e35a-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8e35a-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
