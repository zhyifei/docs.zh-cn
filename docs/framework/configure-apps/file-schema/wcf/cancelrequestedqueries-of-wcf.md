---
title: "WCF 的 &lt;cancelRequestedQueries&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7a5501965f746fe85ad07e396f005beb8e12f3d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="0cb04-102">WCF 的 &lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="0cb04-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="0cb04-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="0cb04-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="0cb04-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="0cb04-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="0cb04-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="0cb04-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
 <span data-ttu-id="0cb04-106">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="0cb04-106">\<system.serviceModel></span></span>  
<span data-ttu-id="0cb04-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="0cb04-107">\<tracking></span></span>  
<span data-ttu-id="0cb04-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="0cb04-108">\<trackingProfile></span></span>  
<span data-ttu-id="0cb04-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="0cb04-109">\<workflow></span></span>  
<span data-ttu-id="0cb04-110">\<cancelRequestedQueries ></span><span class="sxs-lookup"><span data-stu-id="0cb04-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cb04-111">语法</span><span class="sxs-lookup"><span data-stu-id="0cb04-111">Syntax</span></span>  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="0cb04-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0cb04-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0cb04-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0cb04-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0cb04-114">特性</span><span class="sxs-lookup"><span data-stu-id="0cb04-114">Attributes</span></span>  
 <span data-ttu-id="0cb04-115">无。</span><span class="sxs-lookup"><span data-stu-id="0cb04-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0cb04-116">子元素</span><span class="sxs-lookup"><span data-stu-id="0cb04-116">Child Elements</span></span>  
  
|<span data-ttu-id="0cb04-117">元素</span><span class="sxs-lookup"><span data-stu-id="0cb04-117">Element</span></span>|<span data-ttu-id="0cb04-118">描述</span><span class="sxs-lookup"><span data-stu-id="0cb04-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cb04-119">\<cancelRequestedQuery ></span><span class="sxs-lookup"><span data-stu-id="0cb04-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="0cb04-120">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="0cb04-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0cb04-121">父元素</span><span class="sxs-lookup"><span data-stu-id="0cb04-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0cb04-122">元素</span><span class="sxs-lookup"><span data-stu-id="0cb04-122">Element</span></span>|<span data-ttu-id="0cb04-123">描述</span><span class="sxs-lookup"><span data-stu-id="0cb04-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0cb04-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="0cb04-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="0cb04-125">一个配置元素，包含 `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="0cb04-125">A configuration element that contains all queries for a specific workflow identified by the `a HYPERLINK "http://msdn.microsoft.com/en-us/library/system.servicemodel.activities.tracking.configuration.profileworkflowelement.activitydefinitionid(VS.100).aspx" ctivityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0cb04-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb04-126">See Also</span></span>  
 <xref:System.Activities.Tracking.CancelRequestedQuery>  
 [<span data-ttu-id="0cb04-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="0cb04-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="0cb04-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="0cb04-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
