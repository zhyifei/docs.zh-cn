---
title: <customTrackingQueries> WCF 的
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 8b317cc289853902592e145e34b6e7bf5f84763b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704162"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="5d07c-102">\<customTrackingQueries > 的 WCF</span><span class="sxs-lookup"><span data-stu-id="5d07c-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="5d07c-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="5d07c-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="5d07c-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="5d07c-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="5d07c-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="5d07c-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="5d07c-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5d07c-106">\<system.serviceModel></span></span>  
<span data-ttu-id="5d07c-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="5d07c-107">\<tracking></span></span>  
<span data-ttu-id="5d07c-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="5d07c-108">\<profiles></span></span>  
<span data-ttu-id="5d07c-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="5d07c-109">\<trackingProfile></span></span>  
<span data-ttu-id="5d07c-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5d07c-110">\<workflow></span></span>  
<span data-ttu-id="5d07c-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="5d07c-111">\<customTrackingQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d07c-112">语法</span><span class="sxs-lookup"><span data-stu-id="5d07c-112">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d07c-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5d07c-113">Attributes and elements</span></span>

<span data-ttu-id="5d07c-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5d07c-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d07c-115">特性</span><span class="sxs-lookup"><span data-stu-id="5d07c-115">Attributes</span></span>

<span data-ttu-id="5d07c-116">无。</span><span class="sxs-lookup"><span data-stu-id="5d07c-116">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="5d07c-117">子元素</span><span class="sxs-lookup"><span data-stu-id="5d07c-117">Child elements</span></span>
  
|<span data-ttu-id="5d07c-118">元素</span><span class="sxs-lookup"><span data-stu-id="5d07c-118">Element</span></span>|<span data-ttu-id="5d07c-119">描述</span><span class="sxs-lookup"><span data-stu-id="5d07c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d07c-120">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="5d07c-120">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="5d07c-121">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="5d07c-121">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d07c-122">父元素</span><span class="sxs-lookup"><span data-stu-id="5d07c-122">Parent elements</span></span>  
  
|<span data-ttu-id="5d07c-123">元素</span><span class="sxs-lookup"><span data-stu-id="5d07c-123">Element</span></span>|<span data-ttu-id="5d07c-124">描述</span><span class="sxs-lookup"><span data-stu-id="5d07c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d07c-125">\<workflow></span><span class="sxs-lookup"><span data-stu-id="5d07c-125">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="5d07c-126">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="5d07c-126">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5d07c-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d07c-127">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="5d07c-128">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="5d07c-128">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="5d07c-129">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="5d07c-129">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
