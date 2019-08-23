---
title: <variable>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 46cc8cbc-10ec-4625-8813-3f5cd6c6afde
ms.openlocfilehash: a8f66f950db1edf8cd6ec21400785fb7e01b878e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69947275"
---
# <a name="variable"></a><span data-ttu-id="6f191-101">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="6f191-101">\<variable></span></span>
<span data-ttu-id="6f191-102">表示与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="6f191-102">Represents a collection of variables associated with this activity query.</span></span>  
  
 <span data-ttu-id="6f191-103">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="6f191-103">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="6f191-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6f191-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6f191-105">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="6f191-105">\<tracking></span></span>  
<span data-ttu-id="6f191-106">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="6f191-106">\<profiles></span></span>  
<span data-ttu-id="6f191-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6f191-107">\<trackingProfile></span></span>  
<span data-ttu-id="6f191-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="6f191-108">\<workflow></span></span>  
<span data-ttu-id="6f191-109">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="6f191-109">\<activityStateQueries></span></span>  
<span data-ttu-id="6f191-110">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="6f191-110">\<activityStateQuery></span></span>  
<span data-ttu-id="6f191-111">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="6f191-111">\<variables></span></span>  
<span data-ttu-id="6f191-112">\<变量 ></span><span class="sxs-lookup"><span data-stu-id="6f191-112">\<variable></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f191-113">语法</span><span class="sxs-lookup"><span data-stu-id="6f191-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f191-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6f191-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6f191-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6f191-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f191-116">特性</span><span class="sxs-lookup"><span data-stu-id="6f191-116">Attributes</span></span>  
  
|<span data-ttu-id="6f191-117">特性</span><span class="sxs-lookup"><span data-stu-id="6f191-117">Attribute</span></span>|<span data-ttu-id="6f191-118">描述</span><span class="sxs-lookup"><span data-stu-id="6f191-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f191-119">NAME</span><span class="sxs-lookup"><span data-stu-id="6f191-119">name</span></span>|<span data-ttu-id="6f191-120">一个字符串，指定变量的名称。</span><span class="sxs-lookup"><span data-stu-id="6f191-120">A string that specifies the name of the variable.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f191-121">子元素</span><span class="sxs-lookup"><span data-stu-id="6f191-121">Child Elements</span></span>  
 <span data-ttu-id="6f191-122">无。</span><span class="sxs-lookup"><span data-stu-id="6f191-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f191-123">父元素</span><span class="sxs-lookup"><span data-stu-id="6f191-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6f191-124">元素</span><span class="sxs-lookup"><span data-stu-id="6f191-124">Element</span></span>|<span data-ttu-id="6f191-125">描述</span><span class="sxs-lookup"><span data-stu-id="6f191-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6f191-126">\<variable></span><span class="sxs-lookup"><span data-stu-id="6f191-126">\<variable></span></span>](variable.md)|<span data-ttu-id="6f191-127">与活动状态查询相关联的变量。</span><span class="sxs-lookup"><span data-stu-id="6f191-127">A variable associated with an activity state query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f191-128">备注</span><span class="sxs-lookup"><span data-stu-id="6f191-128">Remarks</span></span>  
 <span data-ttu-id="6f191-129">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="6f191-129">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="6f191-130">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="6f191-130">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="6f191-131">您可以使用[ \<参数 >](arguments.md)、 [ \<状态 >](states.md)和[ \<状态 >](states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="6f191-131">You can use the [\<arguments>](arguments.md), [\<states>](states.md) and [\<states>](states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="6f191-132">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="6f191-132">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="6f191-133">变量和参数只能通过 ActivityStateRecord 提取, 因此使用[ \<activityStateQuery >](activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="6f191-133">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6f191-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f191-134">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.VariableElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6f191-135">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6f191-135">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6f191-136">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6f191-136">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
