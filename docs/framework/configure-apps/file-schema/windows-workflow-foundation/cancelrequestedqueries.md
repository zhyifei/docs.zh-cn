---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 628dbf801cae5f61dc7d518c27df3380dd2d3d23
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945949"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="4c4bc-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="4c4bc-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="4c4bc-102">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="4c4bc-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4c4bc-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="4c4bc-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="4c4bc-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4c4bc-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4c4bc-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4c4bc-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4c4bc-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="4c4bc-106">\<tracking></span></span>  
<span data-ttu-id="4c4bc-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4c4bc-107">\<trackingProfile></span></span>  
<span data-ttu-id="4c4bc-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="4c4bc-108">\<workflow></span></span>  
<span data-ttu-id="4c4bc-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="4c4bc-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c4bc-110">语法</span><span class="sxs-lookup"><span data-stu-id="4c4bc-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c4bc-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4c4bc-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4c4bc-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4c4bc-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c4bc-113">特性</span><span class="sxs-lookup"><span data-stu-id="4c4bc-113">Attributes</span></span>  
 <span data-ttu-id="4c4bc-114">无。</span><span class="sxs-lookup"><span data-stu-id="4c4bc-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4c4bc-115">子元素</span><span class="sxs-lookup"><span data-stu-id="4c4bc-115">Child Elements</span></span>  
  
|<span data-ttu-id="4c4bc-116">元素</span><span class="sxs-lookup"><span data-stu-id="4c4bc-116">Element</span></span>|<span data-ttu-id="4c4bc-117">描述</span><span class="sxs-lookup"><span data-stu-id="4c4bc-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c4bc-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="4c4bc-118">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="4c4bc-119">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="4c4bc-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4c4bc-120">父元素</span><span class="sxs-lookup"><span data-stu-id="4c4bc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4c4bc-121">元素</span><span class="sxs-lookup"><span data-stu-id="4c4bc-121">Element</span></span>|<span data-ttu-id="4c4bc-122">描述</span><span class="sxs-lookup"><span data-stu-id="4c4bc-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c4bc-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="4c4bc-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="4c4bc-124">一个配置元素, 该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="4c4bc-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4c4bc-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c4bc-125">See also</span></span>

- [<span data-ttu-id="4c4bc-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="4c4bc-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="4c4bc-127">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4c4bc-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
