---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: e487e54ac5c70351d00df4275302bc9f4e92292c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366525"
---
# <a name="variable"></a><span data-ttu-id="6a859-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="6a859-101">\<variable></span></span>
<span data-ttu-id="6a859-102">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="6a859-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="6a859-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6a859-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6a859-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6a859-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6a859-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6a859-105">\<tracking></span></span>  
<span data-ttu-id="6a859-106">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="6a859-106">\<profiles></span></span>  
<span data-ttu-id="6a859-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6a859-107">\<trackingProfile></span></span>  
<span data-ttu-id="6a859-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6a859-108">\<workflow></span></span>  
<span data-ttu-id="6a859-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6a859-109">\<activityStateQueries></span></span>  
<span data-ttu-id="6a859-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6a859-110">\<activityStateQuery></span></span>  
<span data-ttu-id="6a859-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="6a859-111">\<variables></span></span>  
<span data-ttu-id="6a859-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="6a859-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a859-113">语法</span><span class="sxs-lookup"><span data-stu-id="6a859-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a859-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6a859-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6a859-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6a859-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a859-116">特性</span><span class="sxs-lookup"><span data-stu-id="6a859-116">Attributes</span></span>  
  
|<span data-ttu-id="6a859-117">特性</span><span class="sxs-lookup"><span data-stu-id="6a859-117">Attribute</span></span>|<span data-ttu-id="6a859-118">描述</span><span class="sxs-lookup"><span data-stu-id="6a859-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a859-119">name</span><span class="sxs-lookup"><span data-stu-id="6a859-119">name</span></span>|<span data-ttu-id="6a859-120">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="6a859-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a859-121">子元素</span><span class="sxs-lookup"><span data-stu-id="6a859-121">Child Elements</span></span>  
 <span data-ttu-id="6a859-122">无。</span><span class="sxs-lookup"><span data-stu-id="6a859-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a859-123">父元素</span><span class="sxs-lookup"><span data-stu-id="6a859-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6a859-124">元素</span><span class="sxs-lookup"><span data-stu-id="6a859-124">Element</span></span>|<span data-ttu-id="6a859-125">描述</span><span class="sxs-lookup"><span data-stu-id="6a859-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a859-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="6a859-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="6a859-127">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="6a859-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a859-128">备注</span><span class="sxs-lookup"><span data-stu-id="6a859-128">Remarks</span></span>  
 <span data-ttu-id="6a859-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="6a859-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6a859-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="6a859-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6a859-131">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="6a859-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="6a859-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="6a859-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6a859-133">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="6a859-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6a859-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a859-134">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6a859-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6a859-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6a859-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6a859-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
