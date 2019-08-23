---
title: <customTrackingQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: b034727dc89b58794ec2834cb0ff39cd7e5f1dca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919365"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="ac347-102">\<WCF 的 customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="ac347-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="ac347-103">表示一个查询, 该查询用于跟踪您在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="ac347-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="ac347-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="ac347-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="ac347-105">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="ac347-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="ac347-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ac347-106">\<system.serviceModel></span></span>  
<span data-ttu-id="ac347-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="ac347-107">\<tracking></span></span>  
<span data-ttu-id="ac347-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="ac347-108">\<profiles></span></span>  
<span data-ttu-id="ac347-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="ac347-109">\<trackingProfile></span></span>  
<span data-ttu-id="ac347-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="ac347-110">\<workflow></span></span>  
<span data-ttu-id="ac347-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ac347-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="ac347-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="ac347-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac347-113">语法</span><span class="sxs-lookup"><span data-stu-id="ac347-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac347-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac347-114">Attributes and elements</span></span>  

<span data-ttu-id="ac347-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac347-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac347-116">特性</span><span class="sxs-lookup"><span data-stu-id="ac347-116">Attributes</span></span>  
  
|<span data-ttu-id="ac347-117">特性</span><span class="sxs-lookup"><span data-stu-id="ac347-117">Attribute</span></span>|<span data-ttu-id="ac347-118">描述</span><span class="sxs-lookup"><span data-stu-id="ac347-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="ac347-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="ac347-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="ac347-120">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="ac347-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac347-121">子元素</span><span class="sxs-lookup"><span data-stu-id="ac347-121">Child elements</span></span>

<span data-ttu-id="ac347-122">无。</span><span class="sxs-lookup"><span data-stu-id="ac347-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="ac347-123">父元素</span><span class="sxs-lookup"><span data-stu-id="ac347-123">Parent elements</span></span>

|<span data-ttu-id="ac347-124">元素</span><span class="sxs-lookup"><span data-stu-id="ac347-124">Element</span></span>|<span data-ttu-id="ac347-125">描述</span><span class="sxs-lookup"><span data-stu-id="ac347-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac347-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="ac347-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="ac347-127">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="ac347-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="ac347-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac347-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="ac347-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="ac347-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="ac347-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="ac347-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
