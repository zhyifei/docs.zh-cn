---
title: '&lt;variable&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: 185e7e7196f6679ec3d1fae8a2a256b934022ca9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647876"
---
# <a name="ltvariablegt"></a><span data-ttu-id="ff984-102">&lt;variable&gt;</span><span class="sxs-lookup"><span data-stu-id="ff984-102">&lt;variable&gt;</span></span>
<span data-ttu-id="ff984-103">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="ff984-103">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="ff984-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ff984-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ff984-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ff984-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ff984-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ff984-106">\<tracking></span></span>  
<span data-ttu-id="ff984-107">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="ff984-107">\<profiles></span></span>  
<span data-ttu-id="ff984-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ff984-108">\<trackingProfile></span></span>  
<span data-ttu-id="ff984-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ff984-109">\<workflow></span></span>  
<span data-ttu-id="ff984-110">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ff984-110">\<activityStateQueries></span></span>  
<span data-ttu-id="ff984-111">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ff984-111">\<activityStateQuery></span></span>  
<span data-ttu-id="ff984-112">\<variables></span><span class="sxs-lookup"><span data-stu-id="ff984-112">\<variables></span></span>  
<span data-ttu-id="ff984-113">\<variable></span><span class="sxs-lookup"><span data-stu-id="ff984-113">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff984-114">语法</span><span class="sxs-lookup"><span data-stu-id="ff984-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ff984-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ff984-115">Attributes and Elements</span></span>  
 <span data-ttu-id="ff984-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ff984-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ff984-117">特性</span><span class="sxs-lookup"><span data-stu-id="ff984-117">Attributes</span></span>  
  
|<span data-ttu-id="ff984-118">特性</span><span class="sxs-lookup"><span data-stu-id="ff984-118">Attribute</span></span>|<span data-ttu-id="ff984-119">描述</span><span class="sxs-lookup"><span data-stu-id="ff984-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ff984-120">name</span><span class="sxs-lookup"><span data-stu-id="ff984-120">name</span></span>|<span data-ttu-id="ff984-121">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ff984-121">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ff984-122">子元素</span><span class="sxs-lookup"><span data-stu-id="ff984-122">Child Elements</span></span>  
 <span data-ttu-id="ff984-123">无。</span><span class="sxs-lookup"><span data-stu-id="ff984-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ff984-124">父元素</span><span class="sxs-lookup"><span data-stu-id="ff984-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ff984-125">元素</span><span class="sxs-lookup"><span data-stu-id="ff984-125">Element</span></span>|<span data-ttu-id="ff984-126">描述</span><span class="sxs-lookup"><span data-stu-id="ff984-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ff984-127">\<variable></span><span class="sxs-lookup"><span data-stu-id="ff984-127">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="ff984-128">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="ff984-128">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff984-129">备注</span><span class="sxs-lookup"><span data-stu-id="ff984-129">Remarks</span></span>  
 <span data-ttu-id="ff984-130">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="ff984-130">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ff984-131">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="ff984-131">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ff984-132">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="ff984-132">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ff984-133">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="ff984-133">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ff984-134">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="ff984-134">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ff984-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff984-135">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ff984-136">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ff984-136">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ff984-137">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ff984-137">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
