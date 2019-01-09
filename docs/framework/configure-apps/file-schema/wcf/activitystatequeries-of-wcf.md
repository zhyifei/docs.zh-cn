---
title: WCF 的 &lt;activityStateQueries&gt;
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 2dabfdd248006de60b5e84e739f78e03f364dde3
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146181"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a><span data-ttu-id="f16fb-102">WCF 的 &lt;activityStateQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="f16fb-102">&lt;activityStateQueries&gt; of WCF</span></span>

<span data-ttu-id="f16fb-103">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="f16fb-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f16fb-104">例如，你可能想要跟踪的每次在"发送电子邮件"活动完成工作流实例内。</span><span class="sxs-lookup"><span data-stu-id="f16fb-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f16fb-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="f16fb-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="f16fb-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="f16fb-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="f16fb-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="f16fb-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="f16fb-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f16fb-108">\<system.serviceModel></span></span>  
<span data-ttu-id="f16fb-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="f16fb-109">\<tracking></span></span>  
<span data-ttu-id="f16fb-110">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="f16fb-110">\<profiles></span></span>  
<span data-ttu-id="f16fb-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f16fb-111">\<trackingProfile></span></span>  
<span data-ttu-id="f16fb-112">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="f16fb-112">\<workflow></span></span>  
<span data-ttu-id="f16fb-113">\<activityStateQueries ></span><span class="sxs-lookup"><span data-stu-id="f16fb-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="f16fb-114">语法</span><span class="sxs-lookup"><span data-stu-id="f16fb-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="f16fb-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f16fb-115">Attributes and elements</span></span>

<span data-ttu-id="f16fb-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f16fb-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f16fb-117">特性</span><span class="sxs-lookup"><span data-stu-id="f16fb-117">Attributes</span></span>  

<span data-ttu-id="f16fb-118">无。</span><span class="sxs-lookup"><span data-stu-id="f16fb-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="f16fb-119">子元素</span><span class="sxs-lookup"><span data-stu-id="f16fb-119">Child elements</span></span>

|<span data-ttu-id="f16fb-120">元素</span><span class="sxs-lookup"><span data-stu-id="f16fb-120">Element</span></span>|<span data-ttu-id="f16fb-121">描述</span><span class="sxs-lookup"><span data-stu-id="f16fb-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f16fb-122">\<activityStateQuery ></span><span class="sxs-lookup"><span data-stu-id="f16fb-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="f16fb-123">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="f16fb-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f16fb-124">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="f16fb-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f16fb-125">父元素</span><span class="sxs-lookup"><span data-stu-id="f16fb-125">Parent elements</span></span>

|<span data-ttu-id="f16fb-126">元素</span><span class="sxs-lookup"><span data-stu-id="f16fb-126">Element</span></span>|<span data-ttu-id="f16fb-127">描述</span><span class="sxs-lookup"><span data-stu-id="f16fb-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f16fb-128">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="f16fb-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f16fb-129">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="f16fb-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="f16fb-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f16fb-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
- <xref:System.Activities.Tracking.ActivityStateQuery>    
- [<span data-ttu-id="f16fb-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="f16fb-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [<span data-ttu-id="f16fb-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="f16fb-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
