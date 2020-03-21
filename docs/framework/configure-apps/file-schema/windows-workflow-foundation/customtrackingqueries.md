---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 6901244009956a499458858bf73f8fd83ec52e13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152256"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="1d29a-101">\<自定义跟踪查询></span><span class="sxs-lookup"><span data-stu-id="1d29a-101">\<customTrackingQueries></span></span>
<span data-ttu-id="1d29a-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="1d29a-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="1d29a-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="1d29a-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="1d29a-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="1d29a-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="1d29a-105">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1d29a-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1d29a-106">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d29a-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="1d29a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪>**](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="1d29a-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="1d29a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<跟踪配置文件>**](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="1d29a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="1d29a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<工作流>**](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="1d29a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="1d29a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<自定义跟踪查询>**</span><span class="sxs-lookup"><span data-stu-id="1d29a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d29a-111">语法</span><span class="sxs-lookup"><span data-stu-id="1d29a-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <customTrackingQueries>
        <customTrackingQuery activityName="String"
                             name="String" />
      </customTrackingQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d29a-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1d29a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1d29a-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1d29a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d29a-114">属性</span><span class="sxs-lookup"><span data-stu-id="1d29a-114">Attributes</span></span>  
 <span data-ttu-id="1d29a-115">无。</span><span class="sxs-lookup"><span data-stu-id="1d29a-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d29a-116">子元素</span><span class="sxs-lookup"><span data-stu-id="1d29a-116">Child Elements</span></span>  
  
|<span data-ttu-id="1d29a-117">元素</span><span class="sxs-lookup"><span data-stu-id="1d29a-117">Element</span></span>|<span data-ttu-id="1d29a-118">说明</span><span class="sxs-lookup"><span data-stu-id="1d29a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d29a-119">\<自定义跟踪查询></span><span class="sxs-lookup"><span data-stu-id="1d29a-119">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="1d29a-120">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="1d29a-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d29a-121">父元素</span><span class="sxs-lookup"><span data-stu-id="1d29a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1d29a-122">元素</span><span class="sxs-lookup"><span data-stu-id="1d29a-122">Element</span></span>|<span data-ttu-id="1d29a-123">说明</span><span class="sxs-lookup"><span data-stu-id="1d29a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d29a-124">\<工作流></span><span class="sxs-lookup"><span data-stu-id="1d29a-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="1d29a-125">包含**活动定义 Id**属性标识的特定工作流的所有查询的配置元素。</span><span class="sxs-lookup"><span data-stu-id="1d29a-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d29a-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d29a-126">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="1d29a-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1d29a-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="1d29a-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1d29a-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
