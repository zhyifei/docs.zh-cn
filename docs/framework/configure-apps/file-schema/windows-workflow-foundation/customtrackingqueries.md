---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: 757bbe500ec3edccef465b7ff23b2c974e4a5011
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54598836"
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="267ca-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="267ca-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="267ca-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="267ca-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="267ca-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="267ca-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="267ca-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="267ca-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="267ca-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="267ca-106">\<system.serviceModel></span></span>  
<span data-ttu-id="267ca-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="267ca-107">\<tracking></span></span>  
<span data-ttu-id="267ca-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="267ca-108">\<trackingProfile></span></span>  
<span data-ttu-id="267ca-109">\<workflow></span><span class="sxs-lookup"><span data-stu-id="267ca-109">\<workflow></span></span>  
<span data-ttu-id="267ca-110">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="267ca-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="267ca-111">语法</span><span class="sxs-lookup"><span data-stu-id="267ca-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="267ca-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="267ca-112">Attributes and Elements</span></span>  
 <span data-ttu-id="267ca-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="267ca-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="267ca-114">特性</span><span class="sxs-lookup"><span data-stu-id="267ca-114">Attributes</span></span>  
 <span data-ttu-id="267ca-115">无。</span><span class="sxs-lookup"><span data-stu-id="267ca-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="267ca-116">子元素</span><span class="sxs-lookup"><span data-stu-id="267ca-116">Child Elements</span></span>  
  
|<span data-ttu-id="267ca-117">元素</span><span class="sxs-lookup"><span data-stu-id="267ca-117">Element</span></span>|<span data-ttu-id="267ca-118">描述</span><span class="sxs-lookup"><span data-stu-id="267ca-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="267ca-119">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="267ca-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="267ca-120">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="267ca-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="267ca-121">父元素</span><span class="sxs-lookup"><span data-stu-id="267ca-121">Parent Elements</span></span>  
  
|<span data-ttu-id="267ca-122">元素</span><span class="sxs-lookup"><span data-stu-id="267ca-122">Element</span></span>|<span data-ttu-id="267ca-123">描述</span><span class="sxs-lookup"><span data-stu-id="267ca-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="267ca-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="267ca-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="267ca-125">一个配置元素，包含由标识为特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="267ca-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="267ca-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="267ca-126">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="267ca-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="267ca-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="267ca-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="267ca-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
