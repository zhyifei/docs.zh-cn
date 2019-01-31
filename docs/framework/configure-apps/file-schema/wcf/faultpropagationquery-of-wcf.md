---
title: <faultPropagationQuery> WCF 的
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: 1670f8fdf72bc202a4a595034f3818ab43b11be6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276050"
---
# <a name="faultpropagationquery-of-wcf"></a><span data-ttu-id="8db23-102">\<faultPropagationQuery > 的 WCF</span><span class="sxs-lookup"><span data-stu-id="8db23-102">\<faultPropagationQuery> of WCF</span></span>

<span data-ttu-id="8db23-103">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="8db23-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8db23-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="8db23-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="8db23-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="8db23-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="8db23-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="8db23-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="8db23-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="8db23-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8db23-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8db23-108">\<system.serviceModel></span></span>  
<span data-ttu-id="8db23-109">\<tracking></span><span class="sxs-lookup"><span data-stu-id="8db23-109">\<tracking></span></span>  
<span data-ttu-id="8db23-110">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="8db23-110">\<profiles></span></span>  
<span data-ttu-id="8db23-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8db23-111">\<trackingProfile></span></span>  
<span data-ttu-id="8db23-112">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8db23-112">\<workflow></span></span>  
<span data-ttu-id="8db23-113">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="8db23-113">\<faultPropagationQueries></span></span>  
<span data-ttu-id="8db23-114">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="8db23-114">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8db23-115">语法</span><span class="sxs-lookup"><span data-stu-id="8db23-115">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8db23-116">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8db23-116">Attributes and elements</span></span>

<span data-ttu-id="8db23-117">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8db23-117">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8db23-118">特性</span><span class="sxs-lookup"><span data-stu-id="8db23-118">Attributes</span></span>  
  
|<span data-ttu-id="8db23-119">特性</span><span class="sxs-lookup"><span data-stu-id="8db23-119">Attribute</span></span>|<span data-ttu-id="8db23-120">描述</span><span class="sxs-lookup"><span data-stu-id="8db23-120">Description</span></span>|  
|---------------|-----------------|  
|`faultSourceActivityName`|<span data-ttu-id="8db23-121">一个字符串，指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="8db23-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="8db23-122">默认值是\*，这指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="8db23-122">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|`faultHandlerActivityName`|<span data-ttu-id="8db23-123">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="8db23-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8db23-124">子元素</span><span class="sxs-lookup"><span data-stu-id="8db23-124">Child elements</span></span>

<span data-ttu-id="8db23-125">无。</span><span class="sxs-lookup"><span data-stu-id="8db23-125">None.</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="8db23-126">父元素</span><span class="sxs-lookup"><span data-stu-id="8db23-126">Parent elements</span></span>  
  
|<span data-ttu-id="8db23-127">元素</span><span class="sxs-lookup"><span data-stu-id="8db23-127">Element</span></span>|<span data-ttu-id="8db23-128">描述</span><span class="sxs-lookup"><span data-stu-id="8db23-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8db23-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="8db23-129">\<faultPropagationQueries></span></span>](faultpropagationqueries-of-wcf.md)|<span data-ttu-id="8db23-130">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="8db23-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="8db23-131">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="8db23-131">This event occurs each time a FaultHandler processes a fault.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="8db23-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="8db23-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8db23-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8db23-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8db23-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8db23-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
