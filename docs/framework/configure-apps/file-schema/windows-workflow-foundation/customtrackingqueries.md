---
title: '&lt;customTrackingQueries&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e9e732d-911d-45a3-a569-4b5e9cd1ffbe
ms.openlocfilehash: aa1e7ff4d53cbd40b168c3cc800a23dbcddc28f5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomtrackingqueriesgt"></a><span data-ttu-id="a7569-102">&lt;customTrackingQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="a7569-102">&lt;customTrackingQueries&gt;</span></span>
<span data-ttu-id="a7569-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="a7569-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="a7569-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="a7569-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="a7569-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="a7569-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="a7569-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a7569-106">\<system.serviceModel></span></span>  
<span data-ttu-id="a7569-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="a7569-107">\<tracking></span></span>  
<span data-ttu-id="a7569-108">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="a7569-108">\<trackingProfile></span></span>  
<span data-ttu-id="a7569-109">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="a7569-109">\<workflow></span></span>  
<span data-ttu-id="a7569-110">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="a7569-110">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7569-111">语法</span><span class="sxs-lookup"><span data-stu-id="a7569-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7569-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a7569-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a7569-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a7569-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7569-114">特性</span><span class="sxs-lookup"><span data-stu-id="a7569-114">Attributes</span></span>  
 <span data-ttu-id="a7569-115">无。</span><span class="sxs-lookup"><span data-stu-id="a7569-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a7569-116">子元素</span><span class="sxs-lookup"><span data-stu-id="a7569-116">Child Elements</span></span>  
  
|<span data-ttu-id="a7569-117">元素</span><span class="sxs-lookup"><span data-stu-id="a7569-117">Element</span></span>|<span data-ttu-id="a7569-118">描述</span><span class="sxs-lookup"><span data-stu-id="a7569-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7569-119">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="a7569-119">\<customTrackingQuery></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|<span data-ttu-id="a7569-120">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="a7569-120">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7569-121">父元素</span><span class="sxs-lookup"><span data-stu-id="a7569-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a7569-122">元素</span><span class="sxs-lookup"><span data-stu-id="a7569-122">Element</span></span>|<span data-ttu-id="a7569-123">描述</span><span class="sxs-lookup"><span data-stu-id="a7569-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a7569-124">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="a7569-124">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="a7569-125">一个配置元素，包含由标识的特定工作流的所有查询**activityDefinitionId**属性。</span><span class="sxs-lookup"><span data-stu-id="a7569-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7569-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7569-126">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>       
 [<span data-ttu-id="a7569-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="a7569-127">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="a7569-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="a7569-128">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
