---
title: WCF 的 &lt;customTrackingQuery&gt;
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 234703e677f838dcdccdf857ba38b8729d25a488
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146376"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a><span data-ttu-id="d91b0-102">WCF 的 &lt;customTrackingQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="d91b0-102">&lt;customTrackingQuery&gt; of WCF</span></span>

<span data-ttu-id="d91b0-103">表示用于跟踪你代码活动中定义的事件的查询。</span><span class="sxs-lookup"><span data-stu-id="d91b0-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="d91b0-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="d91b0-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="d91b0-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="d91b0-105">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="d91b0-106">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="d91b0-106">\<system.serviceModel></span></span>  
<span data-ttu-id="d91b0-107">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="d91b0-107">\<tracking></span></span>  
<span data-ttu-id="d91b0-108">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="d91b0-108">\<profiles></span></span>  
<span data-ttu-id="d91b0-109">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="d91b0-109">\<trackingProfile></span></span>  
<span data-ttu-id="d91b0-110">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="d91b0-110">\<workflow></span></span>  
<span data-ttu-id="d91b0-111">\<customTrackingQueries ></span><span class="sxs-lookup"><span data-stu-id="d91b0-111">\<customTrackingQueries></span></span>  
<span data-ttu-id="d91b0-112">\<customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="d91b0-112">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d91b0-113">语法</span><span class="sxs-lookup"><span data-stu-id="d91b0-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d91b0-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d91b0-114">Attributes and elements</span></span>  

<span data-ttu-id="d91b0-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d91b0-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d91b0-116">特性</span><span class="sxs-lookup"><span data-stu-id="d91b0-116">Attributes</span></span>  
  
|<span data-ttu-id="d91b0-117">特性</span><span class="sxs-lookup"><span data-stu-id="d91b0-117">Attribute</span></span>|<span data-ttu-id="d91b0-118">描述</span><span class="sxs-lookup"><span data-stu-id="d91b0-118">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="d91b0-119">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="d91b0-119">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="d91b0-120">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="d91b0-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d91b0-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d91b0-121">Child elements</span></span>

<span data-ttu-id="d91b0-122">无。</span><span class="sxs-lookup"><span data-stu-id="d91b0-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d91b0-123">父元素</span><span class="sxs-lookup"><span data-stu-id="d91b0-123">Parent elements</span></span>

|<span data-ttu-id="d91b0-124">元素</span><span class="sxs-lookup"><span data-stu-id="d91b0-124">Element</span></span>|<span data-ttu-id="d91b0-125">描述</span><span class="sxs-lookup"><span data-stu-id="d91b0-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d91b0-126">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="d91b0-126">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="d91b0-127">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="d91b0-127">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="d91b0-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d91b0-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="d91b0-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="d91b0-129">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="d91b0-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="d91b0-130">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
