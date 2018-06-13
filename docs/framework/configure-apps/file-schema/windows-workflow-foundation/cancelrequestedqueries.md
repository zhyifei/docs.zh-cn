---
title: '&lt;cancelRequestedQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 2abb2dc05bfec4419ca49d1517084ebc208e81e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32757016"
---
# <a name="ltcancelrequestedqueriesgt"></a><span data-ttu-id="4296d-102">&lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="4296d-102">&lt;cancelRequestedQueries&gt;</span></span>
<span data-ttu-id="4296d-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="4296d-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="4296d-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="4296d-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="4296d-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="4296d-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="4296d-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4296d-106">\<system.serviceModel></span></span>  
<span data-ttu-id="4296d-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="4296d-107">\<tracking></span></span>  
<span data-ttu-id="4296d-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="4296d-108">\<trackingProfile></span></span>  
<span data-ttu-id="4296d-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="4296d-109">\<workflow></span></span>  
<span data-ttu-id="4296d-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="4296d-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4296d-111">语法</span><span class="sxs-lookup"><span data-stu-id="4296d-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4296d-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4296d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4296d-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4296d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4296d-114">特性</span><span class="sxs-lookup"><span data-stu-id="4296d-114">Attributes</span></span>  
 <span data-ttu-id="4296d-115">无。</span><span class="sxs-lookup"><span data-stu-id="4296d-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4296d-116">子元素</span><span class="sxs-lookup"><span data-stu-id="4296d-116">Child Elements</span></span>  
  
|<span data-ttu-id="4296d-117">元素</span><span class="sxs-lookup"><span data-stu-id="4296d-117">Element</span></span>|<span data-ttu-id="4296d-118">描述</span><span class="sxs-lookup"><span data-stu-id="4296d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4296d-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="4296d-119">\<cancelRequestedQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/cancelrequestedquery.md)|<span data-ttu-id="4296d-120">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="4296d-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4296d-121">父元素</span><span class="sxs-lookup"><span data-stu-id="4296d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4296d-122">元素</span><span class="sxs-lookup"><span data-stu-id="4296d-122">Element</span></span>|<span data-ttu-id="4296d-123">描述</span><span class="sxs-lookup"><span data-stu-id="4296d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4296d-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="4296d-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="4296d-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="4296d-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4296d-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="4296d-126">See Also</span></span>  
 [<span data-ttu-id="4296d-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="4296d-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="4296d-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4296d-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
