---
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 1a6899eaa04ad16192e07f4bc2ad1abe6e4aedd5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257360"
---
# <a name="faultpropagationquery"></a><span data-ttu-id="c531d-101">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c531d-101">\<faultPropagationQuery></span></span>
<span data-ttu-id="c531d-102">表示一个用于跟踪在活动中发生的错误的处理的查询。</span><span class="sxs-lookup"><span data-stu-id="c531d-102">Represents a query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c531d-103">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="c531d-103">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="c531d-104">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="c531d-104">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="c531d-105">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="c531d-105">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
 <span data-ttu-id="c531d-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="c531d-106">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="c531d-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c531d-107">\<system.serviceModel></span></span>  
<span data-ttu-id="c531d-108">\<tracking></span><span class="sxs-lookup"><span data-stu-id="c531d-108">\<tracking></span></span>  
<span data-ttu-id="c531d-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c531d-109">\<trackingProfile></span></span>  
<span data-ttu-id="c531d-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c531d-110">\<workflow></span></span>  
<span data-ttu-id="c531d-111">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c531d-111">\<faultPropagationQueries></span></span>  
<span data-ttu-id="c531d-112">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c531d-112">\<faultPropagationQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c531d-113">语法</span><span class="sxs-lookup"><span data-stu-id="c531d-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c531d-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c531d-114">Attributes and Elements</span></span>  
 <span data-ttu-id="c531d-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c531d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c531d-116">特性</span><span class="sxs-lookup"><span data-stu-id="c531d-116">Attributes</span></span>  
  
|<span data-ttu-id="c531d-117">特性</span><span class="sxs-lookup"><span data-stu-id="c531d-117">Attribute</span></span>|<span data-ttu-id="c531d-118">描述</span><span class="sxs-lookup"><span data-stu-id="c531d-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c531d-119">activityName</span><span class="sxs-lookup"><span data-stu-id="c531d-119">activityName</span></span>|<span data-ttu-id="c531d-120">一个字符串，指定传播错误的错误处理程序活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c531d-120">A string that specifies the name of the fault hander activity that propagated the fault.</span></span> <span data-ttu-id="c531d-121">默认值为 \*，指示为所有活动返回错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="c531d-121">The default is \*, which indicates that fault propagation records are returned for all activities.</span></span>|  
|<span data-ttu-id="c531d-122">faultHandlerActivityName</span><span class="sxs-lookup"><span data-stu-id="c531d-122">faultHandlerActivityName</span></span>|<span data-ttu-id="c531d-123">一个字符串，指定导致错误的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c531d-123">A string that specifies the name of the activity that was the source of the fault.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c531d-124">子元素</span><span class="sxs-lookup"><span data-stu-id="c531d-124">Child Elements</span></span>  
 <span data-ttu-id="c531d-125">无。</span><span class="sxs-lookup"><span data-stu-id="c531d-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c531d-126">父元素</span><span class="sxs-lookup"><span data-stu-id="c531d-126">Parent Elements</span></span>  
  
|<span data-ttu-id="c531d-127">元素</span><span class="sxs-lookup"><span data-stu-id="c531d-127">Element</span></span>|<span data-ttu-id="c531d-128">描述</span><span class="sxs-lookup"><span data-stu-id="c531d-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c531d-129">\<faultPropagationQueries></span><span class="sxs-lookup"><span data-stu-id="c531d-129">\<faultPropagationQueries></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationqueries.md)|<span data-ttu-id="c531d-130">表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="c531d-130">Represents a list of configuration elements that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="c531d-131">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="c531d-131">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c531d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c531d-132">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="c531d-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c531d-133">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c531d-134">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c531d-134">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
