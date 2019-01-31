---
title: <activityStateQuery> WCF 的
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 97fce512415ad6ae165b29c7e8eff3394d5e675a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254790"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="c9a9f-102">\<activityStateQuery > 的 WCF</span><span class="sxs-lookup"><span data-stu-id="c9a9f-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="c9a9f-103">表示一个查询，该查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="c9a9f-104">例如，你可能想要跟踪的每次在"发送电子邮件"活动完成工作流实例内。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="c9a9f-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="c9a9f-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="c9a9f-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="c9a9f-108">\<system.serviceModel> \<tracking></span><span class="sxs-lookup"><span data-stu-id="c9a9f-108">\<system.serviceModel> \<tracking></span></span>  
<span data-ttu-id="c9a9f-109">\<profiles> \<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="c9a9f-109">\<profiles> \<trackingProfile></span></span>  
<span data-ttu-id="c9a9f-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="c9a9f-110">\<workflow></span></span>  
<span data-ttu-id="c9a9f-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="c9a9f-111">\<activityStateQueries></span></span>  
<span data-ttu-id="c9a9f-112">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="c9a9f-112">\<activityStateQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9a9f-113">语法</span><span class="sxs-lookup"><span data-stu-id="c9a9f-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String" />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQuery>
        </activityStateQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9a9f-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c9a9f-114">Attributes and elements</span></span>  

<span data-ttu-id="c9a9f-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9a9f-116">特性</span><span class="sxs-lookup"><span data-stu-id="c9a9f-116">Attributes</span></span>  
  
|<span data-ttu-id="c9a9f-117">特性</span><span class="sxs-lookup"><span data-stu-id="c9a9f-117">Attribute</span></span>|<span data-ttu-id="c9a9f-118">描述</span><span class="sxs-lookup"><span data-stu-id="c9a9f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9a9f-119">activityName</span><span class="sxs-lookup"><span data-stu-id="c9a9f-119">activityName</span></span>|<span data-ttu-id="c9a9f-120">一个字符串，指定要对其筛选 <xref:System.Activities.Tracking.ActivityStateRecord> 实例的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-120">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9a9f-121">子元素</span><span class="sxs-lookup"><span data-stu-id="c9a9f-121">Child elements</span></span>  
  
|<span data-ttu-id="c9a9f-122">元素</span><span class="sxs-lookup"><span data-stu-id="c9a9f-122">Element</span></span>|<span data-ttu-id="c9a9f-123">描述</span><span class="sxs-lookup"><span data-stu-id="c9a9f-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9a9f-124">\<arguments></span><span class="sxs-lookup"><span data-stu-id="c9a9f-124">\<arguments></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|<span data-ttu-id="c9a9f-125">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-125">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="c9a9f-126">\<states></span><span class="sxs-lookup"><span data-stu-id="c9a9f-126">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="c9a9f-127">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-127">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="c9a9f-128">\<states></span><span class="sxs-lookup"><span data-stu-id="c9a9f-128">\<states></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|<span data-ttu-id="c9a9f-129">与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-129">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9a9f-130">父元素</span><span class="sxs-lookup"><span data-stu-id="c9a9f-130">Parent elements</span></span>  
  
|<span data-ttu-id="c9a9f-131">元素</span><span class="sxs-lookup"><span data-stu-id="c9a9f-131">Element</span></span>|<span data-ttu-id="c9a9f-132">描述</span><span class="sxs-lookup"><span data-stu-id="c9a9f-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9a9f-133">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="c9a9f-133">\<faultPropagationQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="c9a9f-134">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-134">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="c9a9f-135">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-135">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9a9f-136">备注</span><span class="sxs-lookup"><span data-stu-id="c9a9f-136">Remarks</span></span>

<span data-ttu-id="c9a9f-137">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-137">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="c9a9f-138">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-138">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="c9a9f-139">可以使用[\<自变量 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)， [\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)并[\<状态 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)元素提取任何变量或参数从工作流中的任何活动。下面的示例演示提取变量和参数的活动状态查询时活动的`Closed`发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-139">You can use the [\<arguments>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) and [\<states>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="c9a9f-140">变量和自变量只能使用 ActivityStateRecord 可以提取并因此内进行订阅跟踪配置文件使用[ \<activityStateQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md)。</span><span class="sxs-lookup"><span data-stu-id="c9a9f-140">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">
  <states>
    <state name="Closed" />
  </states>
  <variables>
    <variable name="FromAddress" />
  </variables>
  <arguments>
    <argument name="Result" />
  </arguments>
</activityStateQuery>
```  
  
## <a name="see-also"></a><span data-ttu-id="c9a9f-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="c9a9f-141">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="c9a9f-142">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="c9a9f-142">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="c9a9f-143">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="c9a9f-143">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
