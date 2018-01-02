---
title: "WCF 的 &lt;activityStateQuery&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: de042732e7957fa6ea8c22d03ff6892ee1e912f5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltactivitystatequerygt-of-wcf"></a><span data-ttu-id="6acde-102">WCF 的 &lt;activityStateQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="6acde-102">&lt;activityStateQuery&gt; of WCF</span></span>
<span data-ttu-id="6acde-103">表示一个查询，该查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="6acde-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="6acde-104">例如，你可能想要跟踪的每次完成工作流实例中的"发送电子邮件"活动。</span><span class="sxs-lookup"><span data-stu-id="6acde-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="6acde-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="6acde-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="6acde-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="6acde-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="6acde-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6acde-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
 <span data-ttu-id="6acde-108">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="6acde-108">\<system.serviceModel></span></span>  
<span data-ttu-id="6acde-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="6acde-109">\<tracking></span></span>  
<span data-ttu-id="6acde-110">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="6acde-110">\<trackingProfile></span></span>  
<span data-ttu-id="6acde-111">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="6acde-111">\<workflow></span></span>  
<span data-ttu-id="6acde-112">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="6acde-112">\<activityStateQueries></span></span>  
<span data-ttu-id="6acde-113">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="6acde-113">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6acde-114">语法</span><span class="sxs-lookup"><span data-stu-id="6acde-114">Syntax</span></span>  
  
```xml  
<tracking>   <trackingProfile name="Name">       <workflow>          <activityStateQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>       </workflow>   </trackingProfile></tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6acde-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6acde-115">Attributes and Elements</span></span>  
 <span data-ttu-id="6acde-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6acde-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6acde-117">特性</span><span class="sxs-lookup"><span data-stu-id="6acde-117">Attributes</span></span>  
  
|<span data-ttu-id="6acde-118">特性</span><span class="sxs-lookup"><span data-stu-id="6acde-118">Attribute</span></span>|<span data-ttu-id="6acde-119">描述</span><span class="sxs-lookup"><span data-stu-id="6acde-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6acde-120">activityName</span><span class="sxs-lookup"><span data-stu-id="6acde-120">activityName</span></span>|<span data-ttu-id="6acde-121">一个字符串，指定要对其筛选 <xref:System.Activities.Tracking.ActivityStateRecord> 实例的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="6acde-121">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6acde-122">子元素</span><span class="sxs-lookup"><span data-stu-id="6acde-122">Child Elements</span></span>  
  
|<span data-ttu-id="6acde-123">元素</span><span class="sxs-lookup"><span data-stu-id="6acde-123">Element</span></span>|<span data-ttu-id="6acde-124">描述</span><span class="sxs-lookup"><span data-stu-id="6acde-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6acde-125">\<自变量 ></span><span class="sxs-lookup"><span data-stu-id="6acde-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="6acde-126">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="6acde-126">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="6acde-127">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="6acde-127">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="6acde-128">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="6acde-128">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="6acde-129">\<状态 ></span><span class="sxs-lookup"><span data-stu-id="6acde-129">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="6acde-130">与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="6acde-130">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6acde-131">父元素</span><span class="sxs-lookup"><span data-stu-id="6acde-131">Parent Elements</span></span>  
  
|<span data-ttu-id="6acde-132">元素</span><span class="sxs-lookup"><span data-stu-id="6acde-132">Element</span></span>|<span data-ttu-id="6acde-133">描述</span><span class="sxs-lookup"><span data-stu-id="6acde-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6acde-134">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="6acde-134">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="6acde-135">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="6acde-135">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="6acde-136">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="6acde-136">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6acde-137">备注</span><span class="sxs-lookup"><span data-stu-id="6acde-137">Remarks</span></span>  
 <span data-ttu-id="6acde-138">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="6acde-138">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6acde-139">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="6acde-139">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6acde-140">你可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)和[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或自变量从工作流中的任何活动。下面的示例演示提取变量和自变量的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="6acde-140">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6acde-141">变量和自变量只能使用 ActivityStateRecord 来提取，并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="6acde-141">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6acde-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="6acde-142">See Also</span></span>  
 <span data-ttu-id="6acde-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement></span><span class="sxs-lookup"><span data-stu-id="6acde-143"><xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement></span></span>    
 <span data-ttu-id="6acde-144"><xref:System.Activities.Tracking.ActivityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6acde-144"><xref:System.Activities.Tracking.ActivityStateQuery></span></span>     
 [<span data-ttu-id="6acde-145">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6acde-145">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="6acde-146">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6acde-146">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
