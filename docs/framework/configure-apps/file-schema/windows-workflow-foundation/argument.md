---
title: <argument>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: a7144d53-8023-4e90-971f-895e016fd58a
ms.openlocfilehash: a920d60d703fe262bee96d75c420c526d54f88ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790320"
---
# <a name="argument"></a><span data-ttu-id="b248f-101">\<自变量 ></span><span class="sxs-lookup"><span data-stu-id="b248f-101">\<argument></span></span>
<span data-ttu-id="b248f-102">一个配置元素，表示与某一活动状态查询关联的参数。</span><span class="sxs-lookup"><span data-stu-id="b248f-102">A configuration element that represents an argument associated with an activity state query.</span></span>  
  
 <span data-ttu-id="b248f-103">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="b248f-103">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="b248f-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b248f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="b248f-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="b248f-105">\<tracking></span></span>  
<span data-ttu-id="b248f-106">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="b248f-106">\<trackingProfile></span></span>  
<span data-ttu-id="b248f-107">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b248f-107">\<workflow></span></span>  
<span data-ttu-id="b248f-108">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="b248f-108">\<activityStateQueries></span></span>  
<span data-ttu-id="b248f-109">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="b248f-109">\<activityStateQuery></span></span>  
<span data-ttu-id="b248f-110">\<自变量 ></span><span class="sxs-lookup"><span data-stu-id="b248f-110">\<arguments></span></span>  
<span data-ttu-id="b248f-111">\<自变量 ></span><span class="sxs-lookup"><span data-stu-id="b248f-111">\<argument></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b248f-112">语法</span><span class="sxs-lookup"><span data-stu-id="b248f-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String"/>
        </arguments>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b248f-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b248f-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b248f-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b248f-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b248f-115">特性</span><span class="sxs-lookup"><span data-stu-id="b248f-115">Attributes</span></span>  
  
|<span data-ttu-id="b248f-116">特性</span><span class="sxs-lookup"><span data-stu-id="b248f-116">Attribute</span></span>|<span data-ttu-id="b248f-117">描述</span><span class="sxs-lookup"><span data-stu-id="b248f-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b248f-118">name</span><span class="sxs-lookup"><span data-stu-id="b248f-118">name</span></span>|<span data-ttu-id="b248f-119">一个字符串，指定该参数的名称。</span><span class="sxs-lookup"><span data-stu-id="b248f-119">A string that specifies the name of the argument.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b248f-120">子元素</span><span class="sxs-lookup"><span data-stu-id="b248f-120">Child Elements</span></span>  
 <span data-ttu-id="b248f-121">无。</span><span class="sxs-lookup"><span data-stu-id="b248f-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b248f-122">父元素</span><span class="sxs-lookup"><span data-stu-id="b248f-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b248f-123">元素</span><span class="sxs-lookup"><span data-stu-id="b248f-123">Element</span></span>|<span data-ttu-id="b248f-124">描述</span><span class="sxs-lookup"><span data-stu-id="b248f-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b248f-125">\<arguments></span><span class="sxs-lookup"><span data-stu-id="b248f-125">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="b248f-126">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="b248f-126">A collection of arguments associated with this activity query.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b248f-127">备注</span><span class="sxs-lookup"><span data-stu-id="b248f-127">Remarks</span></span>  
 <span data-ttu-id="b248f-128">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="b248f-128">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="b248f-129">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="b248f-129">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="b248f-130">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。</span><span class="sxs-lookup"><span data-stu-id="b248f-130">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="b248f-131">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="b248f-131">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="b248f-132">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="b248f-132">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b248f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b248f-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ArgumentElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="b248f-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b248f-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b248f-135">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b248f-135">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
