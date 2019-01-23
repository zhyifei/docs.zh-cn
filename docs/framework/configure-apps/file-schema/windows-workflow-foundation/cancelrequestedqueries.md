---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 5bc2e3ffeb93bdfcd45638d6b50e218c03706f42
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520680"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="46e55-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="46e55-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="46e55-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="46e55-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="46e55-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="46e55-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="46e55-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="46e55-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="46e55-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="46e55-106">\<system.serviceModel></span></span>  
<span data-ttu-id="46e55-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="46e55-107">\<tracking></span></span>  
<span data-ttu-id="46e55-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="46e55-108">\<trackingProfile></span></span>  
<span data-ttu-id="46e55-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="46e55-109">\<workflow></span></span>  
<span data-ttu-id="46e55-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="46e55-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e55-111">语法</span><span class="sxs-lookup"><span data-stu-id="46e55-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46e55-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="46e55-112">Attributes and Elements</span></span>  
 <span data-ttu-id="46e55-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="46e55-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46e55-114">特性</span><span class="sxs-lookup"><span data-stu-id="46e55-114">Attributes</span></span>  
 <span data-ttu-id="46e55-115">无。</span><span class="sxs-lookup"><span data-stu-id="46e55-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46e55-116">子元素</span><span class="sxs-lookup"><span data-stu-id="46e55-116">Child Elements</span></span>  
  
|<span data-ttu-id="46e55-117">元素</span><span class="sxs-lookup"><span data-stu-id="46e55-117">Element</span></span>|<span data-ttu-id="46e55-118">描述</span><span class="sxs-lookup"><span data-stu-id="46e55-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46e55-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="46e55-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="46e55-120">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="46e55-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46e55-121">父元素</span><span class="sxs-lookup"><span data-stu-id="46e55-121">Parent Elements</span></span>  
  
|<span data-ttu-id="46e55-122">元素</span><span class="sxs-lookup"><span data-stu-id="46e55-122">Element</span></span>|<span data-ttu-id="46e55-123">描述</span><span class="sxs-lookup"><span data-stu-id="46e55-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46e55-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="46e55-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="46e55-125">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="46e55-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46e55-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="46e55-126">See also</span></span>
- [<span data-ttu-id="46e55-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="46e55-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="46e55-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="46e55-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
