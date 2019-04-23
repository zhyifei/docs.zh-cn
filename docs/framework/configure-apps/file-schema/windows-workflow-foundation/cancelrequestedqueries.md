---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 32a37fb3cc2b93046bea133f351185638b0d7545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163158"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="d974b-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d974b-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="d974b-102">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="d974b-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="d974b-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="d974b-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="d974b-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d974b-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d974b-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d974b-105">\<system.serviceModel></span></span>  
<span data-ttu-id="d974b-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="d974b-106">\<tracking></span></span>  
<span data-ttu-id="d974b-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d974b-107">\<trackingProfile></span></span>  
<span data-ttu-id="d974b-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d974b-108">\<workflow></span></span>  
<span data-ttu-id="d974b-109">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="d974b-109">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d974b-110">语法</span><span class="sxs-lookup"><span data-stu-id="d974b-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d974b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d974b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d974b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d974b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d974b-113">特性</span><span class="sxs-lookup"><span data-stu-id="d974b-113">Attributes</span></span>  
 <span data-ttu-id="d974b-114">无。</span><span class="sxs-lookup"><span data-stu-id="d974b-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d974b-115">子元素</span><span class="sxs-lookup"><span data-stu-id="d974b-115">Child Elements</span></span>  
  
|<span data-ttu-id="d974b-116">元素</span><span class="sxs-lookup"><span data-stu-id="d974b-116">Element</span></span>|<span data-ttu-id="d974b-117">描述</span><span class="sxs-lookup"><span data-stu-id="d974b-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d974b-118">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="d974b-118">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="d974b-119">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="d974b-119">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d974b-120">父元素</span><span class="sxs-lookup"><span data-stu-id="d974b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d974b-121">元素</span><span class="sxs-lookup"><span data-stu-id="d974b-121">Element</span></span>|<span data-ttu-id="d974b-122">描述</span><span class="sxs-lookup"><span data-stu-id="d974b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d974b-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="d974b-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="d974b-124">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="d974b-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d974b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="d974b-125">See also</span></span>

- [<span data-ttu-id="d974b-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="d974b-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d974b-127">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d974b-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
