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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3db57b3332638092fc9f16de5199b65c4efafebd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltvariablegt"></a><span data-ttu-id="b6009-102">&lt;变量&gt;</span><span class="sxs-lookup"><span data-stu-id="b6009-102">&lt;variable&gt;</span></span>
<span data-ttu-id="b6009-103">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="b6009-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="b6009-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b6009-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b6009-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="b6009-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b6009-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="b6009-106">\<tracking></span></span>  
<span data-ttu-id="b6009-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="b6009-107">\<profiles></span></span>  
<span data-ttu-id="b6009-108">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="b6009-108">\<trackingProfile></span></span>  
<span data-ttu-id="b6009-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="b6009-109">\<workflow></span></span>  
<span data-ttu-id="b6009-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="b6009-110">\<activityStateQueries></span></span>  
<span data-ttu-id="b6009-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="b6009-111">\<activityStateQuery></span></span>  
<span data-ttu-id="b6009-112">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="b6009-112">\<variables></span></span>  
<span data-ttu-id="b6009-113">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="b6009-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6009-114">语法</span><span class="sxs-lookup"><span data-stu-id="b6009-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b6009-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b6009-115">Attributes and Elements</span></span>  
 <span data-ttu-id="b6009-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b6009-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b6009-117">特性</span><span class="sxs-lookup"><span data-stu-id="b6009-117">Attributes</span></span>  
  
|<span data-ttu-id="b6009-118">特性</span><span class="sxs-lookup"><span data-stu-id="b6009-118">Attribute</span></span>|<span data-ttu-id="b6009-119">描述</span><span class="sxs-lookup"><span data-stu-id="b6009-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b6009-120">name</span><span class="sxs-lookup"><span data-stu-id="b6009-120">name</span></span>|<span data-ttu-id="b6009-121">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="b6009-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b6009-122">子元素</span><span class="sxs-lookup"><span data-stu-id="b6009-122">Child Elements</span></span>  
 <span data-ttu-id="b6009-123">无。</span><span class="sxs-lookup"><span data-stu-id="b6009-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b6009-124">父元素</span><span class="sxs-lookup"><span data-stu-id="b6009-124">Parent Elements</span></span>  
  
|<span data-ttu-id="b6009-125">元素</span><span class="sxs-lookup"><span data-stu-id="b6009-125">Element</span></span>|<span data-ttu-id="b6009-126">描述</span><span class="sxs-lookup"><span data-stu-id="b6009-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b6009-127">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="b6009-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="b6009-128">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="b6009-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6009-129">备注</span><span class="sxs-lookup"><span data-stu-id="b6009-129">Remarks</span></span>  
 <span data-ttu-id="b6009-130">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="b6009-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b6009-131">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="b6009-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b6009-132">你可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)和[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或自变量从工作流中的任何活动。下面的示例演示提取变量和自变量的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="b6009-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b6009-133">变量和自变量只能使用 ActivityStateRecord 来提取，并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="b6009-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b6009-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6009-134">See Also</span></span>  
 <span data-ttu-id="b6009-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b6009-135"><xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType></span></span>       
 <span data-ttu-id="b6009-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="b6009-136"><xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="b6009-137">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b6009-137">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="b6009-138">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b6009-138">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
