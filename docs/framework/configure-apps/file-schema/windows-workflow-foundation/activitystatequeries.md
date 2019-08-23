---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 6e91078a24a950c6de027d57e3883e38f19447d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945456"
---
# <a name="activitystatequeries"></a><span data-ttu-id="45265-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="45265-101">\<activityStateQueries></span></span>
<span data-ttu-id="45265-102">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="45265-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="45265-103">例如, 你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。</span><span class="sxs-lookup"><span data-stu-id="45265-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="45265-104">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="45265-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="45265-105">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="45265-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="45265-106">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="45265-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="45265-107">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="45265-107">\<system.serviceModel></span></span>  
<span data-ttu-id="45265-108">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="45265-108">\<tracking></span></span>  
<span data-ttu-id="45265-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="45265-109">\<trackingProfile></span></span>  
<span data-ttu-id="45265-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="45265-110">\<workflow></span></span>  
<span data-ttu-id="45265-111">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="45265-111">\<activityStateQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45265-112">语法</span><span class="sxs-lookup"><span data-stu-id="45265-112">Syntax</span></span>  
  
```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityStateQueries>
        <activityStateQuery activityName="String" />
        <arguments>
          <argument name="String" />
        </arguments>
        <states>
          <state name="String" />
        </states>
        <variables>
         <variable name="String" />
        </variables>
      </activityStateQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="45265-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="45265-113">Attributes and Elements</span></span>  
 <span data-ttu-id="45265-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="45265-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="45265-115">特性</span><span class="sxs-lookup"><span data-stu-id="45265-115">Attributes</span></span>  
 <span data-ttu-id="45265-116">无。</span><span class="sxs-lookup"><span data-stu-id="45265-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="45265-117">子元素</span><span class="sxs-lookup"><span data-stu-id="45265-117">Child Elements</span></span>  
  
|<span data-ttu-id="45265-118">元素</span><span class="sxs-lookup"><span data-stu-id="45265-118">Element</span></span>|<span data-ttu-id="45265-119">描述</span><span class="sxs-lookup"><span data-stu-id="45265-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45265-120">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="45265-120">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="45265-121">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="45265-121">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="45265-122">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="45265-122">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="45265-123">父元素</span><span class="sxs-lookup"><span data-stu-id="45265-123">Parent Elements</span></span>  
  
|<span data-ttu-id="45265-124">元素</span><span class="sxs-lookup"><span data-stu-id="45265-124">Element</span></span>|<span data-ttu-id="45265-125">描述</span><span class="sxs-lookup"><span data-stu-id="45265-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="45265-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="45265-126">\<workflow></span></span>](workflow.md)|<span data-ttu-id="45265-127">一个配置元素, 该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="45265-127">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="45265-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="45265-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="45265-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="45265-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="45265-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="45265-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
