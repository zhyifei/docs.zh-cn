---
title: WCF 的 &lt;cancelRequestedQueries&gt;
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 40fbcafd641e93be6ba21635f4f6e6428be62c12
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2018
ms.locfileid: "50032695"
---
# <a name="ltcancelrequestedqueriesgt-of-wcf"></a><span data-ttu-id="6a2ff-102">WCF 的 &lt;cancelRequestedQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="6a2ff-102">&lt;cancelRequestedQueries&gt; of WCF</span></span>
<span data-ttu-id="6a2ff-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6a2ff-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="6a2ff-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6a2ff-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6a2ff-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6a2ff-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6a2ff-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="6a2ff-107">\<tracking></span></span>  
<span data-ttu-id="6a2ff-108">\<配置文件 > \<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6a2ff-108">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="6a2ff-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="6a2ff-109">\<workflow></span></span>  
<span data-ttu-id="6a2ff-110">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="6a2ff-110">\<cancelRequestedQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a2ff-111">语法</span><span class="sxs-lookup"><span data-stu-id="6a2ff-111">Syntax</span></span>  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String"/>
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>  
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6a2ff-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6a2ff-112">Attributes and elements</span></span>  

<span data-ttu-id="6a2ff-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a2ff-114">特性</span><span class="sxs-lookup"><span data-stu-id="6a2ff-114">Attributes</span></span>

<span data-ttu-id="6a2ff-115">无。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-115">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="6a2ff-116">子元素</span><span class="sxs-lookup"><span data-stu-id="6a2ff-116">Child elements</span></span>
  
|<span data-ttu-id="6a2ff-117">元素</span><span class="sxs-lookup"><span data-stu-id="6a2ff-117">Element</span></span>|<span data-ttu-id="6a2ff-118">描述</span><span class="sxs-lookup"><span data-stu-id="6a2ff-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a2ff-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="6a2ff-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="6a2ff-120">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="6a2ff-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a2ff-121">父元素</span><span class="sxs-lookup"><span data-stu-id="6a2ff-121">Parent elements</span></span>  
  
|<span data-ttu-id="6a2ff-122">元素</span><span class="sxs-lookup"><span data-stu-id="6a2ff-122">Element</span></span>|<span data-ttu-id="6a2ff-123">描述</span><span class="sxs-lookup"><span data-stu-id="6a2ff-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a2ff-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="6a2ff-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="6a2ff-125">一个配置元素，包含 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="6a2ff-125">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a2ff-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a2ff-126">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="6a2ff-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6a2ff-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6a2ff-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6a2ff-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
