---
title: <activityStateQueries>WCF 的
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 249ac3d91f6251a943dd856e4122b8b54f691702
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850571"
---
# <a name="activitystatequeries-of-wcf"></a><span data-ttu-id="90e28-102">\<WCF 的 Activitystatequeries&gt ></span><span class="sxs-lookup"><span data-stu-id="90e28-102">\<activityStateQueries> of WCF</span></span>

<span data-ttu-id="90e28-103">表示一个查询集合，这些查询用于跟踪构成工作流实例的活动的生命周期更改。</span><span class="sxs-lookup"><span data-stu-id="90e28-103">Represents a collection of queries that are used to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="90e28-104">例如，你可能想要跟踪每次在工作流实例中完成 "发送电子邮件" 活动的时间。</span><span class="sxs-lookup"><span data-stu-id="90e28-104">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="90e28-105">跟踪参与者需要用此查询来订阅活动状态记录对象。</span><span class="sxs-lookup"><span data-stu-id="90e28-105">This query is necessary for a tracking participant to subscribe to activity state record objects.</span></span> <span data-ttu-id="90e28-106">在 ActivityStates 中指定了要订阅的可用状态。</span><span class="sxs-lookup"><span data-stu-id="90e28-106">The available states to subscribe to are specified in ActivityStates.</span></span>

<span data-ttu-id="90e28-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="90e28-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>

<span data-ttu-id="90e28-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="90e28-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="90e28-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="90e28-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="90e28-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="90e28-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="90e28-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="90e28-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="90e28-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="90e28-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="90e28-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="90e28-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="90e28-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Activitystatequeries&gt >**</span><span class="sxs-lookup"><span data-stu-id="90e28-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityStateQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e28-115">语法</span><span class="sxs-lookup"><span data-stu-id="90e28-115">Syntax</span></span>  
  
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

## <a name="attributes-and-elements"></a><span data-ttu-id="90e28-116">特性和元素</span><span class="sxs-lookup"><span data-stu-id="90e28-116">Attributes and elements</span></span>

<span data-ttu-id="90e28-117">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="90e28-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="90e28-118">特性</span><span class="sxs-lookup"><span data-stu-id="90e28-118">Attributes</span></span>  

<span data-ttu-id="90e28-119">无。</span><span class="sxs-lookup"><span data-stu-id="90e28-119">None.</span></span>  

### <a name="child-elements"></a><span data-ttu-id="90e28-120">子元素</span><span class="sxs-lookup"><span data-stu-id="90e28-120">Child elements</span></span>

|<span data-ttu-id="90e28-121">元素</span><span class="sxs-lookup"><span data-stu-id="90e28-121">Element</span></span>|<span data-ttu-id="90e28-122">描述</span><span class="sxs-lookup"><span data-stu-id="90e28-122">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90e28-123">\<activityStateQuery></span><span class="sxs-lookup"><span data-stu-id="90e28-123">\<activityStateQuery></span></span>](activitystatequery-of-wcf.md)|<span data-ttu-id="90e28-124">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="90e28-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="90e28-125">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="90e28-125">This event occurs each time a FaultHandler processes a fault.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="90e28-126">父元素</span><span class="sxs-lookup"><span data-stu-id="90e28-126">Parent elements</span></span>

|<span data-ttu-id="90e28-127">元素</span><span class="sxs-lookup"><span data-stu-id="90e28-127">Element</span></span>|<span data-ttu-id="90e28-128">描述</span><span class="sxs-lookup"><span data-stu-id="90e28-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90e28-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="90e28-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="90e28-130">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="90e28-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|

## <a name="see-also"></a><span data-ttu-id="90e28-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="90e28-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>
- <xref:System.Activities.Tracking.ActivityStateQuery>
- [<span data-ttu-id="90e28-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="90e28-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="90e28-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="90e28-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
