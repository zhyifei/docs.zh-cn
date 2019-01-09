---
title: WCF 的 &lt;faultPropagationQuery&gt;
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: cf582fce4e899e62daa4f34f193a0232ec19a135
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149028"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a><span data-ttu-id="1a1e5-102">WCF 的 &lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="1a1e5-102">&lt;faultPropagationQuery&gt; of WCF</span></span>

<span data-ttu-id="1a1e5-103">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1a1e5-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="1a1e5-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="1a1e5-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="1a1e5-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="1a1e5-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1a1e5-108">\<system.serviceModel></span></span>  
<span data-ttu-id="1a1e5-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="1a1e5-109">\<tracking></span></span>  
<span data-ttu-id="1a1e5-110">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="1a1e5-110">\<profiles></span></span>  
<span data-ttu-id="1a1e5-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="1a1e5-111">\<trackingProfile></span></span>  
<span data-ttu-id="1a1e5-112">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="1a1e5-112">\<workflow></span></span>  
<span data-ttu-id="1a1e5-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="1a1e5-113">\<faultPropagationQueries></span></span>  
<span data-ttu-id="1a1e5-114">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="1a1e5-114">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a1e5-115">语法</span><span class="sxs-lookup"><span data-stu-id="1a1e5-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String" />
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a1e5-116">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a1e5-116">Attributes and elements</span></span>

<span data-ttu-id="1a1e5-117">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1a1e5-118">特性</span><span class="sxs-lookup"><span data-stu-id="1a1e5-118">Attributes</span></span>  
  
|<span data-ttu-id="1a1e5-119">特性</span><span class="sxs-lookup"><span data-stu-id="1a1e5-119">Attribute</span></span>|<span data-ttu-id="1a1e5-120">描述</span><span class="sxs-lookup"><span data-stu-id="1a1e5-120">Description</span></span>|  
|---------------|-----------------|  
|`faultSourceActivityName`|<span data-ttu-id="1a1e5-121">一个字符串，指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="1a1e5-122">默认值是\*，这指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|`faultHandlerActivityName`|<span data-ttu-id="1a1e5-123">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a1e5-124">子元素</span><span class="sxs-lookup"><span data-stu-id="1a1e5-124">Child elements</span></span>

<span data-ttu-id="1a1e5-125">无。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-125">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="1a1e5-126">父元素</span><span class="sxs-lookup"><span data-stu-id="1a1e5-126">Parent elements</span></span>  
  
|<span data-ttu-id="1a1e5-127">元素</span><span class="sxs-lookup"><span data-stu-id="1a1e5-127">Element</span></span>|<span data-ttu-id="1a1e5-128">描述</span><span class="sxs-lookup"><span data-stu-id="1a1e5-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a1e5-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="1a1e5-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="1a1e5-130">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="1a1e5-131">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="1a1e5-131">This event occurs each time a FaultHandler processes a fault.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="1a1e5-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a1e5-132">See also</span></span>  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1a1e5-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1a1e5-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1a1e5-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1a1e5-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
