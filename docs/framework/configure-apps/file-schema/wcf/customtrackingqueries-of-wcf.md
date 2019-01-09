---
title: WCF 的 &lt;customTrackingQueries&gt;
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: f75c6bf50d30da5a136137c858a5cd96ce0783ff
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150079"
---
# <a name="ltcustomtrackingqueriesgt-of-wcf"></a><span data-ttu-id="e3126-102">WCF 的 &lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="e3126-102">&lt;customTrackingQueries&gt; of WCF</span></span>

<span data-ttu-id="e3126-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e3126-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="e3126-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="e3126-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="e3126-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="e3126-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="e3126-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e3126-106">\<system.serviceModel></span></span>  
<span data-ttu-id="e3126-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="e3126-107">\<tracking></span></span>  
<span data-ttu-id="e3126-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="e3126-108">\<profiles></span></span>  
<span data-ttu-id="e3126-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="e3126-109">\<trackingProfile></span></span>  
<span data-ttu-id="e3126-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e3126-110">\<workflow></span></span>  
<span data-ttu-id="e3126-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="e3126-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3126-112">语法</span><span class="sxs-lookup"><span data-stu-id="e3126-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3126-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3126-113">Attributes and elements</span></span>

<span data-ttu-id="e3126-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e3126-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3126-115">特性</span><span class="sxs-lookup"><span data-stu-id="e3126-115">Attributes</span></span>

<span data-ttu-id="e3126-116">无。</span><span class="sxs-lookup"><span data-stu-id="e3126-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="e3126-117">子元素</span><span class="sxs-lookup"><span data-stu-id="e3126-117">Child elements</span></span>
  
|<span data-ttu-id="e3126-118">元素</span><span class="sxs-lookup"><span data-stu-id="e3126-118">Element</span></span>|<span data-ttu-id="e3126-119">描述</span><span class="sxs-lookup"><span data-stu-id="e3126-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3126-120">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="e3126-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="e3126-121">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="e3126-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3126-122">父元素</span><span class="sxs-lookup"><span data-stu-id="e3126-122">Parent elements</span></span>  
  
|<span data-ttu-id="e3126-123">元素</span><span class="sxs-lookup"><span data-stu-id="e3126-123">Element</span></span>|<span data-ttu-id="e3126-124">描述</span><span class="sxs-lookup"><span data-stu-id="e3126-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e3126-125">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="e3126-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="e3126-126">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="e3126-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3126-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3126-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
- [<span data-ttu-id="e3126-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="e3126-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="e3126-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e3126-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
