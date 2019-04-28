---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: c85f3c57739c48566c97c8b1debfb7f2c3912bdf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61613516"
---
# <a name="variable"></a><span data-ttu-id="ffed3-101">\<variable></span><span class="sxs-lookup"><span data-stu-id="ffed3-101">\<variable></span></span>
<span data-ttu-id="ffed3-102">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="ffed3-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="ffed3-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="ffed3-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="ffed3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ffed3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ffed3-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ffed3-105">\<tracking></span></span>  
<span data-ttu-id="ffed3-106">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="ffed3-106">\<profiles></span></span>  
<span data-ttu-id="ffed3-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ffed3-107">\<trackingProfile></span></span>  
<span data-ttu-id="ffed3-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ffed3-108">\<workflow></span></span>  
<span data-ttu-id="ffed3-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="ffed3-109">\<activityStateQueries></span></span>  
<span data-ttu-id="ffed3-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="ffed3-110">\<activityStateQuery></span></span>  
<span data-ttu-id="ffed3-111">\<variables></span><span class="sxs-lookup"><span data-stu-id="ffed3-111">\<variables></span></span>  
<span data-ttu-id="ffed3-112">\<variable></span><span class="sxs-lookup"><span data-stu-id="ffed3-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffed3-113">语法</span><span class="sxs-lookup"><span data-stu-id="ffed3-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ffed3-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ffed3-114">Attributes and Elements</span></span>  
 <span data-ttu-id="ffed3-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ffed3-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ffed3-116">特性</span><span class="sxs-lookup"><span data-stu-id="ffed3-116">Attributes</span></span>  
  
|<span data-ttu-id="ffed3-117">特性</span><span class="sxs-lookup"><span data-stu-id="ffed3-117">Attribute</span></span>|<span data-ttu-id="ffed3-118">描述</span><span class="sxs-lookup"><span data-stu-id="ffed3-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ffed3-119">name</span><span class="sxs-lookup"><span data-stu-id="ffed3-119">name</span></span>|<span data-ttu-id="ffed3-120">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="ffed3-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ffed3-121">子元素</span><span class="sxs-lookup"><span data-stu-id="ffed3-121">Child Elements</span></span>  
 <span data-ttu-id="ffed3-122">无。</span><span class="sxs-lookup"><span data-stu-id="ffed3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ffed3-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ffed3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="ffed3-124">元素</span><span class="sxs-lookup"><span data-stu-id="ffed3-124">Element</span></span>|<span data-ttu-id="ffed3-125">描述</span><span class="sxs-lookup"><span data-stu-id="ffed3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ffed3-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="ffed3-126">\<variable></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/variable.md)|<span data-ttu-id="ffed3-127">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="ffed3-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffed3-128">备注</span><span class="sxs-lookup"><span data-stu-id="ffed3-128">Remarks</span></span>  
 <span data-ttu-id="ffed3-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="ffed3-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="ffed3-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="ffed3-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="ffed3-131">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="ffed3-131">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="ffed3-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="ffed3-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="ffed3-133">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="ffed3-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ffed3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffed3-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ffed3-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ffed3-135">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ffed3-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ffed3-136">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
