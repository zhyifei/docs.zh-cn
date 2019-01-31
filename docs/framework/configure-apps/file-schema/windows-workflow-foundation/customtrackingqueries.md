---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: a4689e55962cd32d738682129aaa0612a4684384
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264625"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="ce0e0-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ce0e0-101">\<customTrackingQueries></span></span>
<span data-ttu-id="ce0e0-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="ce0e0-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="ce0e0-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="ce0e0-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="ce0e0-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ce0e0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ce0e0-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ce0e0-105">\<system.serviceModel></span></span>  
<span data-ttu-id="ce0e0-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ce0e0-106">\<tracking></span></span>  
<span data-ttu-id="ce0e0-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ce0e0-107">\<trackingProfile></span></span>  
<span data-ttu-id="ce0e0-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ce0e0-108">\<workflow></span></span>  
<span data-ttu-id="ce0e0-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ce0e0-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0e0-110">语法</span><span class="sxs-lookup"><span data-stu-id="ce0e0-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce0e0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ce0e0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce0e0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ce0e0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce0e0-113">特性</span><span class="sxs-lookup"><span data-stu-id="ce0e0-113">Attributes</span></span>  
 <span data-ttu-id="ce0e0-114">无。</span><span class="sxs-lookup"><span data-stu-id="ce0e0-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce0e0-115">子元素</span><span class="sxs-lookup"><span data-stu-id="ce0e0-115">Child Elements</span></span>  
  
|<span data-ttu-id="ce0e0-116">元素</span><span class="sxs-lookup"><span data-stu-id="ce0e0-116">Element</span></span>|<span data-ttu-id="ce0e0-117">描述</span><span class="sxs-lookup"><span data-stu-id="ce0e0-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce0e0-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ce0e0-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="ce0e0-119">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="ce0e0-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce0e0-120">父元素</span><span class="sxs-lookup"><span data-stu-id="ce0e0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ce0e0-121">元素</span><span class="sxs-lookup"><span data-stu-id="ce0e0-121">Element</span></span>|<span data-ttu-id="ce0e0-122">描述</span><span class="sxs-lookup"><span data-stu-id="ce0e0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce0e0-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="ce0e0-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="ce0e0-124">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="ce0e0-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce0e0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce0e0-125">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ce0e0-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ce0e0-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ce0e0-127">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ce0e0-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
