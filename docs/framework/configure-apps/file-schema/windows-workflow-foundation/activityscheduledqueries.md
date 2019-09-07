---
title: <activityScheduledQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ca6e82f1-54f2-48d6-899c-9873065b5547
ms.openlocfilehash: a43242e2f22c48a57c11f6f03657d7d3de27ff48
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398982"
---
# <a name="activityscheduledqueries"></a><span data-ttu-id="8de98-101">\<activityScheduledQueries></span><span class="sxs-lookup"><span data-stu-id="8de98-101">\<activityScheduledQueries></span></span>
<span data-ttu-id="8de98-102">表示一个查询集合，这些查询用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="8de98-102">Represents a collection of queries that are used to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="8de98-103">跟踪参与者需要用此查询来订阅活动安排记录。</span><span class="sxs-lookup"><span data-stu-id="8de98-103">The query is necessary for a tracking participant to subscribe to activity scheduled records.</span></span>  
  
 <span data-ttu-id="8de98-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="8de98-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="8de98-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8de98-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8de98-106">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8de98-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="8de98-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="8de98-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="8de98-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="8de98-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="8de98-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="8de98-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="8de98-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<activityScheduledQueries >**</span><span class="sxs-lookup"><span data-stu-id="8de98-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<activityScheduledQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de98-111">语法</span><span class="sxs-lookup"><span data-stu-id="8de98-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <activityScheduledQueries>
        <activityScheduledQuery activityName="String" 
                                childActivityName="String" />
      </activityScheduledQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8de98-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8de98-112">Attributes and Elements</span></span>  
 <span data-ttu-id="8de98-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8de98-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8de98-114">特性</span><span class="sxs-lookup"><span data-stu-id="8de98-114">Attributes</span></span>  
 <span data-ttu-id="8de98-115">无。</span><span class="sxs-lookup"><span data-stu-id="8de98-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8de98-116">子元素</span><span class="sxs-lookup"><span data-stu-id="8de98-116">Child Elements</span></span>  
  
|<span data-ttu-id="8de98-117">元素</span><span class="sxs-lookup"><span data-stu-id="8de98-117">Element</span></span>|<span data-ttu-id="8de98-118">描述</span><span class="sxs-lookup"><span data-stu-id="8de98-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8de98-119">\<activityScheduledQuery></span><span class="sxs-lookup"><span data-stu-id="8de98-119">\<activityScheduledQuery></span></span>](activityscheduledquery.md)|<span data-ttu-id="8de98-120">一个查询，用于跟踪安排给父活动来执行的活动。</span><span class="sxs-lookup"><span data-stu-id="8de98-120">A query that is used to track an activity scheduled for execution by a parent activity.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8de98-121">父元素</span><span class="sxs-lookup"><span data-stu-id="8de98-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8de98-122">元素</span><span class="sxs-lookup"><span data-stu-id="8de98-122">Element</span></span>|<span data-ttu-id="8de98-123">描述</span><span class="sxs-lookup"><span data-stu-id="8de98-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8de98-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="8de98-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="8de98-125">一个配置元素，该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="8de98-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8de98-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="8de98-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.ActivityScheduledQuery?displayProperty=nameWithType>
- [<span data-ttu-id="8de98-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="8de98-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="8de98-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="8de98-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
