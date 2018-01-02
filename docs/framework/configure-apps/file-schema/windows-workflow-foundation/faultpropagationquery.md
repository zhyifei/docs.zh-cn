---
title: '&lt;faultPropagationQuery&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 244ae0db12964e2baf6de15f545cfa40152ee88e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltfaultpropagationquerygt"></a><span data-ttu-id="3a186-102">&lt;faultPropagationQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="3a186-102">&lt;faultPropagationQuery&gt;</span></span>
<span data-ttu-id="3a186-103">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="3a186-103">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3a186-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="3a186-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="3a186-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="3a186-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="3a186-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="3a186-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="3a186-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="3a186-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="3a186-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="3a186-108">\<system.serviceModel></span></span>  
<span data-ttu-id="3a186-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="3a186-109">\<tracking></span></span>  
<span data-ttu-id="3a186-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="3a186-110">\<trackingProfile></span></span>  
<span data-ttu-id="3a186-111">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="3a186-111">\<workflow></span></span>  
<span data-ttu-id="3a186-112">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3a186-112">\<faultPropagationQueries></span></span>  
<span data-ttu-id="3a186-113">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="3a186-113">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a186-114">语法</span><span class="sxs-lookup"><span data-stu-id="3a186-114">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String" 
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a186-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3a186-115">Attributes and Elements</span></span>  
 <span data-ttu-id="3a186-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3a186-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a186-117">特性</span><span class="sxs-lookup"><span data-stu-id="3a186-117">Attributes</span></span>  
  
|<span data-ttu-id="3a186-118">特性</span><span class="sxs-lookup"><span data-stu-id="3a186-118">Attribute</span></span>|<span data-ttu-id="3a186-119">描述</span><span class="sxs-lookup"><span data-stu-id="3a186-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a186-120">activityName</span><span class="sxs-lookup"><span data-stu-id="3a186-120">activityName</span></span>|<span data-ttu-id="3a186-121">一个字符串，指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="3a186-121">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="3a186-122">默认值为 *，指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="3a186-122">The default is *, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="3a186-123">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="3a186-123">faultHandlerActivityName</span></span>|<span data-ttu-id="3a186-124">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="3a186-124">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3a186-125">子元素</span><span class="sxs-lookup"><span data-stu-id="3a186-125">Child Elements</span></span>  
 <span data-ttu-id="3a186-126">无。</span><span class="sxs-lookup"><span data-stu-id="3a186-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a186-127">父元素</span><span class="sxs-lookup"><span data-stu-id="3a186-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3a186-128">元素</span><span class="sxs-lookup"><span data-stu-id="3a186-128">Element</span></span>|<span data-ttu-id="3a186-129">描述</span><span class="sxs-lookup"><span data-stu-id="3a186-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a186-130">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="3a186-130">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="3a186-131">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="3a186-131">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="3a186-132">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="3a186-132">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a186-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a186-133">See Also</span></span>  
 <span data-ttu-id="3a186-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3a186-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="3a186-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="3a186-135"><xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="3a186-136">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="3a186-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="3a186-137">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="3a186-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
