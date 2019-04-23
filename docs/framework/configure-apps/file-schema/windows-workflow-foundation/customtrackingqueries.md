---
title: <customTrackingQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 663dda571990a86dc71ea927c4e97241e0ed3fc1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120076"
---
# <a name="customtrackingqueries"></a><span data-ttu-id="5ef68-101">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="5ef68-101">\<customTrackingQueries></span></span>
<span data-ttu-id="5ef68-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="5ef68-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5ef68-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="5ef68-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5ef68-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="5ef68-104">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="5ef68-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5ef68-105">\<system.serviceModel></span></span>  
<span data-ttu-id="5ef68-106">\<tracking></span><span class="sxs-lookup"><span data-stu-id="5ef68-106">\<tracking></span></span>  
<span data-ttu-id="5ef68-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5ef68-107">\<trackingProfile></span></span>  
<span data-ttu-id="5ef68-108">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5ef68-108">\<workflow></span></span>  
<span data-ttu-id="5ef68-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="5ef68-109">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef68-110">语法</span><span class="sxs-lookup"><span data-stu-id="5ef68-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ef68-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5ef68-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5ef68-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5ef68-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ef68-113">特性</span><span class="sxs-lookup"><span data-stu-id="5ef68-113">Attributes</span></span>  
 <span data-ttu-id="5ef68-114">无。</span><span class="sxs-lookup"><span data-stu-id="5ef68-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5ef68-115">子元素</span><span class="sxs-lookup"><span data-stu-id="5ef68-115">Child Elements</span></span>  
  
|<span data-ttu-id="5ef68-116">元素</span><span class="sxs-lookup"><span data-stu-id="5ef68-116">Element</span></span>|<span data-ttu-id="5ef68-117">描述</span><span class="sxs-lookup"><span data-stu-id="5ef68-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ef68-118">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="5ef68-118">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="5ef68-119">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="5ef68-119">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5ef68-120">父元素</span><span class="sxs-lookup"><span data-stu-id="5ef68-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5ef68-121">元素</span><span class="sxs-lookup"><span data-stu-id="5ef68-121">Element</span></span>|<span data-ttu-id="5ef68-122">描述</span><span class="sxs-lookup"><span data-stu-id="5ef68-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ef68-123">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5ef68-123">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5ef68-124">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="5ef68-124">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ef68-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ef68-125">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5ef68-126">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="5ef68-126">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5ef68-127">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="5ef68-127">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
