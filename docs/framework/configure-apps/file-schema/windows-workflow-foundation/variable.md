---
title: "&lt;变量&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ad2a4d3768c26755a9437826c70585a43f967d09
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="75c68-102">&lt;变量&gt;</span><span class="sxs-lookup"><span data-stu-id="75c68-102">&lt;variable&gt;</span></span>
<span data-ttu-id="75c68-103">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="75c68-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="75c68-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="75c68-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="75c68-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="75c68-105">\<system.serviceModel></span></span>  
<span data-ttu-id="75c68-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="75c68-106">\<tracking></span></span>  
<span data-ttu-id="75c68-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="75c68-107">\<profiles></span></span>  
<span data-ttu-id="75c68-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="75c68-108">\<trackingProfile></span></span>  
<span data-ttu-id="75c68-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="75c68-109">\<workflow></span></span>  
<span data-ttu-id="75c68-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="75c68-110">\<activityStateQueries></span></span>  
<span data-ttu-id="75c68-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="75c68-111">\<activityStateQuery></span></span>  
<span data-ttu-id="75c68-112">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="75c68-112">\<variables></span></span>  
<span data-ttu-id="75c68-113">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="75c68-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75c68-114">语法</span><span class="sxs-lookup"><span data-stu-id="75c68-114">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <variables>
          <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75c68-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="75c68-115">Attributes and Elements</span></span>  
 <span data-ttu-id="75c68-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="75c68-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75c68-117">特性</span><span class="sxs-lookup"><span data-stu-id="75c68-117">Attributes</span></span>  
  
|<span data-ttu-id="75c68-118">特性</span><span class="sxs-lookup"><span data-stu-id="75c68-118">Attribute</span></span>|<span data-ttu-id="75c68-119">描述</span><span class="sxs-lookup"><span data-stu-id="75c68-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="75c68-120">name</span><span class="sxs-lookup"><span data-stu-id="75c68-120">name</span></span>|<span data-ttu-id="75c68-121">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="75c68-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75c68-122">子元素</span><span class="sxs-lookup"><span data-stu-id="75c68-122">Child Elements</span></span>  
 <span data-ttu-id="75c68-123">无。</span><span class="sxs-lookup"><span data-stu-id="75c68-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75c68-124">父元素</span><span class="sxs-lookup"><span data-stu-id="75c68-124">Parent Elements</span></span>  
  
|<span data-ttu-id="75c68-125">元素</span><span class="sxs-lookup"><span data-stu-id="75c68-125">Element</span></span>|<span data-ttu-id="75c68-126">描述</span><span class="sxs-lookup"><span data-stu-id="75c68-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="75c68-127">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="75c68-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="75c68-128">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="75c68-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75c68-129">备注</span><span class="sxs-lookup"><span data-stu-id="75c68-129">Remarks</span></span>  
 <span data-ttu-id="75c68-130">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="75c68-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="75c68-131">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="75c68-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="75c68-132">你可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)和[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或自变量从工作流中的任何活动。下面的示例演示提取变量和自变量的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="75c68-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="75c68-133">变量和自变量只能使用 ActivityStateRecord 来提取，并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="75c68-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75c68-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75c68-134">See Also</span></span>  
 <span data-ttu-id="75c68-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="75c68-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="75c68-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="75c68-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="75c68-137">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="75c68-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="75c68-138">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="75c68-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
