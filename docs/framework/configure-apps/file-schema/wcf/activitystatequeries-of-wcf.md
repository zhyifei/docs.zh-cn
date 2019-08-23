---
title: <activityStateQueries>WCF 的
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 415cd4a75ecab725f91bcd298f8a7966ea6079d1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920299"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="25c57-102">\<WCF 的 Activitystatequeries&gt ></span><span class="sxs-lookup"><span data-stu-id="25c57-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="25c57-103">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="25c57-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="25c57-104">例如, 你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。</span><span class="sxs-lookup"><span data-stu-id="25c57-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="25c57-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="25c57-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="25c57-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="25c57-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="25c57-107">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="25c57-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="25c57-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="25c57-108">\<system.serviceModel></span></span>  
<span data-ttu-id="25c57-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="25c57-109">\<tracking></span></span>  
<span data-ttu-id="25c57-110">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="25c57-110">\<profiles></span></span>  
<span data-ttu-id="25c57-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="25c57-111">\<trackingProfile></span></span>  
<span data-ttu-id="25c57-112">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="25c57-112">\<workflow></span></span>  
<span data-ttu-id="25c57-113">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="25c57-113">\<activityStateQueries></span></span>  

## <a name="syntax"></a><span data-ttu-id="25c57-114">语法</span><span class="sxs-lookup"><span data-stu-id="25c57-114">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="25c57-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="25c57-115">Attributes and elements</span></span>

<span data-ttu-id="25c57-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="25c57-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="25c57-117">特性</span><span class="sxs-lookup"><span data-stu-id="25c57-117">Attributes</span></span>  

<span data-ttu-id="25c57-118">无。</span><span class="sxs-lookup"><span data-stu-id="25c57-118">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="25c57-119">子元素</span><span class="sxs-lookup"><span data-stu-id="25c57-119">Child elements</span></span>

|<span data-ttu-id="25c57-120">元素</span><span class="sxs-lookup"><span data-stu-id="25c57-120">Element</span></span>|<span data-ttu-id="25c57-121">描述</span><span class="sxs-lookup"><span data-stu-id="25c57-121">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25c57-122">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="25c57-122">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="25c57-123">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="25c57-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="25c57-124">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="25c57-124">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="25c57-125">父元素</span><span class="sxs-lookup"><span data-stu-id="25c57-125">Parent elements</span></span>

|<span data-ttu-id="25c57-126">元素</span><span class="sxs-lookup"><span data-stu-id="25c57-126">Element</span></span>|<span data-ttu-id="25c57-127">描述</span><span class="sxs-lookup"><span data-stu-id="25c57-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="25c57-128">\<workflow></span><span class="sxs-lookup"><span data-stu-id="25c57-128">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="25c57-129">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="25c57-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="25c57-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="25c57-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="25c57-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="25c57-131">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="25c57-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="25c57-132">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
