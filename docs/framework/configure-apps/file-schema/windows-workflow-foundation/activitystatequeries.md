---
title: <activityStateQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: bdd3c8ae-a13f-4df1-9b3c-a9d6c4bb1b5f
ms.openlocfilehash: 58e3752be81609e32eee631e46d10c0a7d704248
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398959"
---
# <a name="activitystatequeries"></a><span data-ttu-id="285cd-101">\<activityStateQueries></span><span class="sxs-lookup"><span data-stu-id="285cd-101">\<activityStateQueries></span></span>
<span data-ttu-id="285cd-102">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="285cd-102">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="285cd-103">例如，你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。</span><span class="sxs-lookup"><span data-stu-id="285cd-103">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="285cd-104">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="285cd-104">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="285cd-105">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="285cd-105">The available states to subscribe to are specified in ActivityStates.</span></span>  
  
 <span data-ttu-id="285cd-106">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="285cd-106">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="285cd-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="285cd-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="285cd-108">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="285cd-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="285cd-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="285cd-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="285cd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="285cd-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="285cd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="285cd-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="285cd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Activitystatequeries&gt >**</span><span class="sxs-lookup"><span data-stu-id="285cd-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="285cd-113">语法</span><span class="sxs-lookup"><span data-stu-id="285cd-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="285cd-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="285cd-114">Attributes and Elements</span></span>  
 <span data-ttu-id="285cd-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="285cd-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="285cd-116">特性</span><span class="sxs-lookup"><span data-stu-id="285cd-116">Attributes</span></span>  
 <span data-ttu-id="285cd-117">无。</span><span class="sxs-lookup"><span data-stu-id="285cd-117">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="285cd-118">子元素</span><span class="sxs-lookup"><span data-stu-id="285cd-118">Child Elements</span></span>  
  
|<span data-ttu-id="285cd-119">元素</span><span class="sxs-lookup"><span data-stu-id="285cd-119">Element</span></span>|<span data-ttu-id="285cd-120">描述</span><span class="sxs-lookup"><span data-stu-id="285cd-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="285cd-121">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="285cd-121">\<activityStateQuery></span></span>](activitystatequery.md)|<span data-ttu-id="285cd-122">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="285cd-122">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="285cd-123">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="285cd-123">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="285cd-124">父元素</span><span class="sxs-lookup"><span data-stu-id="285cd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="285cd-125">元素</span><span class="sxs-lookup"><span data-stu-id="285cd-125">Element</span></span>|<span data-ttu-id="285cd-126">描述</span><span class="sxs-lookup"><span data-stu-id="285cd-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="285cd-127">\<workflow></span><span class="sxs-lookup"><span data-stu-id="285cd-127">\<workflow></span></span>](workflow.md)|<span data-ttu-id="285cd-128">一个配置元素，该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="285cd-128">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="285cd-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="285cd-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityStateQuery?displayProperty=nameWithType>
- [<span data-ttu-id="285cd-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="285cd-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="285cd-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="285cd-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
