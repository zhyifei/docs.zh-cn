---
title: '&lt;变量&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 7d41d80bfe83cfafca01509d50709e21730bcb97
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756782"
---
# <a name="ltvariablegt"></a><span data-ttu-id="8f019-102">&lt;变量&gt;</span><span class="sxs-lookup"><span data-stu-id="8f019-102">&lt;variable&gt;</span></span>
<span data-ttu-id="8f019-103">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="8f019-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="8f019-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="8f019-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="8f019-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8f019-105">\<system.serviceModel></span></span>  
<span data-ttu-id="8f019-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="8f019-106">\<tracking></span></span>  
<span data-ttu-id="8f019-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="8f019-107">\<profiles></span></span>  
<span data-ttu-id="8f019-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="8f019-108">\<trackingProfile></span></span>  
<span data-ttu-id="8f019-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="8f019-109">\<workflow></span></span>  
<span data-ttu-id="8f019-110">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="8f019-110">\<activityStateQueries></span></span>  
<span data-ttu-id="8f019-111">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="8f019-111">\<activityStateQuery></span></span>  
<span data-ttu-id="8f019-112">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="8f019-112">\<variables></span></span>  
<span data-ttu-id="8f019-113">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="8f019-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f019-114">语法</span><span class="sxs-lookup"><span data-stu-id="8f019-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f019-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8f019-115">Attributes and Elements</span></span>  
 <span data-ttu-id="8f019-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8f019-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f019-117">特性</span><span class="sxs-lookup"><span data-stu-id="8f019-117">Attributes</span></span>  
  
|<span data-ttu-id="8f019-118">特性</span><span class="sxs-lookup"><span data-stu-id="8f019-118">Attribute</span></span>|<span data-ttu-id="8f019-119">描述</span><span class="sxs-lookup"><span data-stu-id="8f019-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f019-120">name</span><span class="sxs-lookup"><span data-stu-id="8f019-120">name</span></span>|<span data-ttu-id="8f019-121">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="8f019-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f019-122">子元素</span><span class="sxs-lookup"><span data-stu-id="8f019-122">Child Elements</span></span>  
 <span data-ttu-id="8f019-123">无。</span><span class="sxs-lookup"><span data-stu-id="8f019-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8f019-124">父元素</span><span class="sxs-lookup"><span data-stu-id="8f019-124">Parent Elements</span></span>  
  
|<span data-ttu-id="8f019-125">元素</span><span class="sxs-lookup"><span data-stu-id="8f019-125">Element</span></span>|<span data-ttu-id="8f019-126">描述</span><span class="sxs-lookup"><span data-stu-id="8f019-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f019-127">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="8f019-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="8f019-128">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="8f019-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f019-129">备注</span><span class="sxs-lookup"><span data-stu-id="8f019-129">Remarks</span></span>  
 <span data-ttu-id="8f019-130">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="8f019-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="8f019-131">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="8f019-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="8f019-132">你可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)和[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或自变量从工作流中的任何活动。下面的示例演示提取变量和自变量的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="8f019-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="8f019-133">变量和自变量只能使用 ActivityStateRecord 来提取，并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="8f019-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f019-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f019-134">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="8f019-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8f019-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="8f019-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8f019-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
