---
title: '&lt;cancelRequestedQueries&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b3699985095fca59d5817a31c52b29fe7609a2e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="e5c65-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="e5c65-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="e5c65-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="e5c65-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="e5c65-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="e5c65-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="e5c65-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="e5c65-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="e5c65-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e5c65-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e5c65-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e5c65-107">\<tracking></span></span>  
<span data-ttu-id="e5c65-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="e5c65-108">\<trackingProfile></span></span>  
<span data-ttu-id="e5c65-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e5c65-109">\<workflow></span></span>  
<span data-ttu-id="e5c65-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="e5c65-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c65-111">语法</span><span class="sxs-lookup"><span data-stu-id="e5c65-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5c65-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e5c65-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e5c65-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e5c65-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5c65-114">特性</span><span class="sxs-lookup"><span data-stu-id="e5c65-114">Attributes</span></span>  
 <span data-ttu-id="e5c65-115">无。</span><span class="sxs-lookup"><span data-stu-id="e5c65-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e5c65-116">子元素</span><span class="sxs-lookup"><span data-stu-id="e5c65-116">Child Elements</span></span>  
  
|<span data-ttu-id="e5c65-117">元素</span><span class="sxs-lookup"><span data-stu-id="e5c65-117">Element</span></span>|<span data-ttu-id="e5c65-118">描述</span><span class="sxs-lookup"><span data-stu-id="e5c65-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5c65-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="e5c65-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="e5c65-120">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="e5c65-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5c65-121">父元素</span><span class="sxs-lookup"><span data-stu-id="e5c65-121">Parent Elements</span></span>  
  
|<span data-ttu-id="e5c65-122">元素</span><span class="sxs-lookup"><span data-stu-id="e5c65-122">Element</span></span>|<span data-ttu-id="e5c65-123">描述</span><span class="sxs-lookup"><span data-stu-id="e5c65-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5c65-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e5c65-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e5c65-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="e5c65-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e5c65-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5c65-126">See Also</span></span>  
 [<span data-ttu-id="e5c65-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e5c65-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="e5c65-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e5c65-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
