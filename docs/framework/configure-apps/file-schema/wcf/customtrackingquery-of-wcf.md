---
title: <customTrackingQuery> WCF 的
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 0a5e7c034ce1ef12a8d7d5b1753e2e441e48e293
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673168"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="6bfcb-102">\<customTrackingQuery > 的 WCF</span><span class="sxs-lookup"><span data-stu-id="6bfcb-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="6bfcb-103">表示用于跟踪你代码活动中定义的事件的查询。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="6bfcb-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="6bfcb-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="6bfcb-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="6bfcb-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6bfcb-106">\<system.serviceModel></span></span>  
<span data-ttu-id="6bfcb-107">\<tracking></span><span class="sxs-lookup"><span data-stu-id="6bfcb-107">\<tracking></span></span>  
<span data-ttu-id="6bfcb-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="6bfcb-108">\<profiles></span></span>  
<span data-ttu-id="6bfcb-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="6bfcb-109">\<trackingProfile></span></span>  
<span data-ttu-id="6bfcb-110">\<workflow></span><span class="sxs-lookup"><span data-stu-id="6bfcb-110">\<workflow></span></span>  
<span data-ttu-id="6bfcb-111">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6bfcb-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="6bfcb-112">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="6bfcb-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bfcb-113">语法</span><span class="sxs-lookup"><span data-stu-id="6bfcb-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bfcb-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="6bfcb-114">Attributes and elements</span></span>  

<span data-ttu-id="6bfcb-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bfcb-116">特性</span><span class="sxs-lookup"><span data-stu-id="6bfcb-116">Attributes</span></span>  
  
|<span data-ttu-id="6bfcb-117">特性</span><span class="sxs-lookup"><span data-stu-id="6bfcb-117">Attribute</span></span>|<span data-ttu-id="6bfcb-118">描述</span><span class="sxs-lookup"><span data-stu-id="6bfcb-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="6bfcb-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="6bfcb-120">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bfcb-121">子元素</span><span class="sxs-lookup"><span data-stu-id="6bfcb-121">Child elements</span></span>

<span data-ttu-id="6bfcb-122">无。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6bfcb-123">父元素</span><span class="sxs-lookup"><span data-stu-id="6bfcb-123">Parent elements</span></span>

|<span data-ttu-id="6bfcb-124">元素</span><span class="sxs-lookup"><span data-stu-id="6bfcb-124">Element</span></span>|<span data-ttu-id="6bfcb-125">描述</span><span class="sxs-lookup"><span data-stu-id="6bfcb-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bfcb-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="6bfcb-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="6bfcb-127">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="6bfcb-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="6bfcb-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bfcb-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="6bfcb-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6bfcb-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6bfcb-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6bfcb-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
