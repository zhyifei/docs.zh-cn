---
title: "&lt;states&gt; 的 &lt;state&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0985c9ea84cc29b1cb8883411d3b9b1e52de97b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltstategt-of-ltstatesgt"></a><span data-ttu-id="4ea27-102">&lt;states&gt; 的 &lt;state&gt;</span><span class="sxs-lookup"><span data-stu-id="4ea27-102">&lt;state&gt; of &lt;states&gt;</span></span>
<span data-ttu-id="4ea27-103">一个配置元素，该元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="4ea27-103">A configuration element that contains the state of the subscribed activity for which a tracking record should be emitted.</span></span>  
  
 <span data-ttu-id="4ea27-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea27-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="4ea27-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4ea27-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4ea27-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="4ea27-106">\<tracking></span></span>  
<span data-ttu-id="4ea27-107">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4ea27-107">\<trackingProfile></span></span>  
<span data-ttu-id="4ea27-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="4ea27-108">\<workflow></span></span>  
<span data-ttu-id="4ea27-109">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="4ea27-109">\<activityStateQueries></span></span>  
<span data-ttu-id="4ea27-110">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="4ea27-110">\<activityStateQuery></span></span>  
<span data-ttu-id="4ea27-111">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="4ea27-111">\<states></span></span>  
<span data-ttu-id="4ea27-112">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="4ea27-112">\<state></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ea27-113">语法</span><span class="sxs-lookup"><span data-stu-id="4ea27-113">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <states>
          <state name="String" />
        </states>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ea27-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4ea27-114">Attributes and Elements</span></span>  
 <span data-ttu-id="4ea27-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4ea27-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ea27-116">特性</span><span class="sxs-lookup"><span data-stu-id="4ea27-116">Attributes</span></span>  
  
|<span data-ttu-id="4ea27-117">特性</span><span class="sxs-lookup"><span data-stu-id="4ea27-117">Attribute</span></span>|<span data-ttu-id="4ea27-118">描述</span><span class="sxs-lookup"><span data-stu-id="4ea27-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4ea27-119">name</span><span class="sxs-lookup"><span data-stu-id="4ea27-119">name</span></span>|<span data-ttu-id="4ea27-120">一个字符串，指定应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="4ea27-120">A string that specifies the state of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ea27-121">子元素</span><span class="sxs-lookup"><span data-stu-id="4ea27-121">Child Elements</span></span>  
 <span data-ttu-id="4ea27-122">无。</span><span class="sxs-lookup"><span data-stu-id="4ea27-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ea27-123">父元素</span><span class="sxs-lookup"><span data-stu-id="4ea27-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4ea27-124">元素</span><span class="sxs-lookup"><span data-stu-id="4ea27-124">Element</span></span>|<span data-ttu-id="4ea27-125">描述</span><span class="sxs-lookup"><span data-stu-id="4ea27-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ea27-126">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="4ea27-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|<span data-ttu-id="4ea27-127">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="4ea27-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ea27-128">备注</span><span class="sxs-lookup"><span data-stu-id="4ea27-128">Remarks</span></span>  
 <span data-ttu-id="4ea27-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="4ea27-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="4ea27-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="4ea27-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="4ea27-131">你可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)和[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或自变量从工作流中的任何活动。下面的示例演示提取变量和自变量的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="4ea27-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="4ea27-132">变量和自变量只能使用 ActivityStateRecord 来提取，并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea27-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ea27-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ea27-133">See Also</span></span>  
 <span data-ttu-id="4ea27-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4ea27-134"><xref:System.ServiceModel.Activities.Tracking.Configuration.StateElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="4ea27-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4ea27-135"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="4ea27-136">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="4ea27-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="4ea27-137">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="4ea27-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
