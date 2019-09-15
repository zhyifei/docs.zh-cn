---
title: <activityStateQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
ms.openlocfilehash: 49c507424e813067e1dad9b08167d9661acef36f
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991220"
---
# <a name="activitystatequery-of-wcf"></a><span data-ttu-id="af6aa-102">\<WCF 的 activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="af6aa-102">\<activityStateQuery> of WCF</span></span>

<span data-ttu-id="af6aa-103">表示一个查询，该查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="af6aa-103">Represents a query that is used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="af6aa-104">例如，你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。</span><span class="sxs-lookup"><span data-stu-id="af6aa-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="af6aa-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="af6aa-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="af6aa-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="af6aa-106">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
<span data-ttu-id="af6aa-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="af6aa-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="af6aa-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af6aa-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af6aa-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="af6aa-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="af6aa-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af6aa-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="af6aa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="af6aa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="af6aa-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af6aa-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="af6aa-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af6aa-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="af6aa-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Activitystatequeries&gt >** ](activitystatequeries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="af6aa-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<activityStateQueries>**](activitystatequeries-of-wcf.md)</span></span>\
<span data-ttu-id="af6aa-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityStateQuery >**</span><span class="sxs-lookup"><span data-stu-id="af6aa-115">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af6aa-116">语法</span><span class="sxs-lookup"><span data-stu-id="af6aa-116">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af6aa-117">特性和元素</span><span class="sxs-lookup"><span data-stu-id="af6aa-117">Attributes and elements</span></span>  

<span data-ttu-id="af6aa-118">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="af6aa-118">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af6aa-119">特性</span><span class="sxs-lookup"><span data-stu-id="af6aa-119">Attributes</span></span>  
  
|<span data-ttu-id="af6aa-120">特性</span><span class="sxs-lookup"><span data-stu-id="af6aa-120">Attribute</span></span>|<span data-ttu-id="af6aa-121">描述</span><span class="sxs-lookup"><span data-stu-id="af6aa-121">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af6aa-122">activityName</span><span class="sxs-lookup"><span data-stu-id="af6aa-122">activityName</span></span>|<span data-ttu-id="af6aa-123">一个字符串，指定要对其筛选 <xref:System.Activities.Tracking.ActivityStateRecord> 实例的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="af6aa-123">A string that specifies the name of the activity to filter <xref:System.Activities.Tracking.ActivityStateRecord> instances on.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af6aa-124">子元素</span><span class="sxs-lookup"><span data-stu-id="af6aa-124">Child elements</span></span>  
  
|<span data-ttu-id="af6aa-125">元素</span><span class="sxs-lookup"><span data-stu-id="af6aa-125">Element</span></span>|<span data-ttu-id="af6aa-126">描述</span><span class="sxs-lookup"><span data-stu-id="af6aa-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af6aa-127">\<参数 ></span><span class="sxs-lookup"><span data-stu-id="af6aa-127">\<arguments></span></span>](../windows-workflow-foundation/arguments.md)|<span data-ttu-id="af6aa-128">与此活动查询关联的自变量的集合。</span><span class="sxs-lookup"><span data-stu-id="af6aa-128">A collection of arguments associated with this activity query.</span></span>|  
|[<span data-ttu-id="af6aa-129">\<states></span><span class="sxs-lookup"><span data-stu-id="af6aa-129">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="af6aa-130">一个配置元素集合，这些元素包含应为其发出跟踪记录的已订阅活动的状态。</span><span class="sxs-lookup"><span data-stu-id="af6aa-130">A collection of configuration elements that contain the states of the subscribed activity for which a tracking record should be emitted.</span></span>|  
|[<span data-ttu-id="af6aa-131">\<states></span><span class="sxs-lookup"><span data-stu-id="af6aa-131">\<states></span></span>](../windows-workflow-foundation/states.md)|<span data-ttu-id="af6aa-132">与此活动查询关联的变量的集合。</span><span class="sxs-lookup"><span data-stu-id="af6aa-132">A collection of variables associated with this activity query.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="af6aa-133">父元素</span><span class="sxs-lookup"><span data-stu-id="af6aa-133">Parent elements</span></span>  
  
|<span data-ttu-id="af6aa-134">元素</span><span class="sxs-lookup"><span data-stu-id="af6aa-134">Element</span></span>|<span data-ttu-id="af6aa-135">描述</span><span class="sxs-lookup"><span data-stu-id="af6aa-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="af6aa-136">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="af6aa-136">\<faultPropagationQuery></span></span>](../windows-workflow-foundation/faultpropagationquery.md)|<span data-ttu-id="af6aa-137">表示一个配置元素列表，这些元素用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="af6aa-137">Represents a list of configuration elements that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="af6aa-138">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="af6aa-138">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af6aa-139">备注</span><span class="sxs-lookup"><span data-stu-id="af6aa-139">Remarks</span></span>

<span data-ttu-id="af6aa-140">ActivityStateQuery 的一项独特功能是能够在跟踪工作流的执行时提取数据。</span><span class="sxs-lookup"><span data-stu-id="af6aa-140">One unique feature of an ActivityStateQuery is the ability to extract data when tracking the execution of a workflow.</span></span> <span data-ttu-id="af6aa-141">这在访问跟踪记录后续执行时可提供其他上下文。</span><span class="sxs-lookup"><span data-stu-id="af6aa-141">This provides additional context when accessing the tracking records post execution.</span></span> <span data-ttu-id="af6aa-142">您可以使用[ \<参数 >](../windows-workflow-foundation/arguments.md)、 [ \<状态 >](../windows-workflow-foundation/states.md)和[ \<状态 >](../windows-workflow-foundation/states.md)元素从工作流中的任何活动提取任何变量或参数。</span><span class="sxs-lookup"><span data-stu-id="af6aa-142">You can use the [\<arguments>](../windows-workflow-foundation/arguments.md), [\<states>](../windows-workflow-foundation/states.md) and [\<states>](../windows-workflow-foundation/states.md) elements to extract any variable or argument from any activity in a workflow.</span></span> <span data-ttu-id="af6aa-143">下面的示例演示用于在发出活动的 `Closed` 跟踪记录时提取变量和自变量的活动状态查询。</span><span class="sxs-lookup"><span data-stu-id="af6aa-143">The following example shows an activity state query that extracts variables and arguments when the activity’s `Closed` tracking record is emitted.</span></span> <span data-ttu-id="af6aa-144">变量和参数只能通过 ActivityStateRecord 提取，因此使用[ \<activityStateQuery >](../windows-workflow-foundation/activitystatequery.md)在跟踪配置文件内进行订阅。</span><span class="sxs-lookup"><span data-stu-id="af6aa-144">Variables and arguments can be extracted only with an ActivityStateRecord and thus are subscribed to within a tracking profile using [\<activityStateQuery>](../windows-workflow-foundation/activitystatequery.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af6aa-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="af6aa-145">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="af6aa-146">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="af6aa-146">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="af6aa-147">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="af6aa-147">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
