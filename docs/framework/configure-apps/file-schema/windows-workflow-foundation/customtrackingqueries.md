---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 429940b2ed69d8be497626f634a21adca540b529
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945843"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="7351f-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="7351f-101">\<customTrackingQueries></span></span>
<span data-ttu-id="7351f-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="7351f-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="7351f-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="7351f-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="7351f-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="7351f-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="7351f-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="7351f-105">\<system.serviceModel></span></span>  
<span data-ttu-id="7351f-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="7351f-106">\<tracking></span></span>  
<span data-ttu-id="7351f-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="7351f-107">\<trackingProfile></span></span>  
<span data-ttu-id="7351f-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="7351f-108">\<workflow></span></span>  
<span data-ttu-id="7351f-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="7351f-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7351f-110">语法</span><span class="sxs-lookup"><span data-stu-id="7351f-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7351f-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7351f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7351f-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7351f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7351f-113">特性</span><span class="sxs-lookup"><span data-stu-id="7351f-113">Attributes</span></span>  
 <span data-ttu-id="7351f-114">无。</span><span class="sxs-lookup"><span data-stu-id="7351f-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="7351f-115">子元素</span><span class="sxs-lookup"><span data-stu-id="7351f-115">Child Elements</span></span>  
  
|<span data-ttu-id="7351f-116">元素</span><span class="sxs-lookup"><span data-stu-id="7351f-116">Element</span></span>|<span data-ttu-id="7351f-117">描述</span><span class="sxs-lookup"><span data-stu-id="7351f-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7351f-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="7351f-118">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="7351f-119">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="7351f-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7351f-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7351f-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7351f-121">元素</span><span class="sxs-lookup"><span data-stu-id="7351f-121">Element</span></span>|<span data-ttu-id="7351f-122">描述</span><span class="sxs-lookup"><span data-stu-id="7351f-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7351f-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="7351f-123">\<workflow></span></span>](workflow.md)|<span data-ttu-id="7351f-124">一个配置元素, 该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="7351f-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7351f-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7351f-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="7351f-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="7351f-126">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="7351f-127">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="7351f-127">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
