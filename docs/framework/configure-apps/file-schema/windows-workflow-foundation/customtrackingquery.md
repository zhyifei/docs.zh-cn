---
title: <customTrackingQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4e108e89-1132-46b7-868a-c7f5c69dc89f
ms.openlocfilehash: 9605f5d050baf046ff3c549c19191934299a65e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945756"
---
# <a name="customtrackingquery"></a><span data-ttu-id="f4361-101">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f4361-101">\<customTrackingQuery></span></span>
<span data-ttu-id="f4361-102">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="f4361-102">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="f4361-103">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="f4361-103">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
 <span data-ttu-id="f4361-104">有关跟踪配置文件查询的详细信息, 请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f4361-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="f4361-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f4361-105">\<system.serviceModel></span></span>  
<span data-ttu-id="f4361-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="f4361-106">\<tracking></span></span>  
<span data-ttu-id="f4361-107">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f4361-107">\<trackingProfile></span></span>  
<span data-ttu-id="f4361-108">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="f4361-108">\<workflow></span></span>  
<span data-ttu-id="f4361-109">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="f4361-109">\<customTrackingQueries></span></span>  
<span data-ttu-id="f4361-110">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f4361-110">\<customTrackingQuery></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4361-111">语法</span><span class="sxs-lookup"><span data-stu-id="f4361-111">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4361-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f4361-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f4361-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f4361-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4361-114">特性</span><span class="sxs-lookup"><span data-stu-id="f4361-114">Attributes</span></span>  
  
|<span data-ttu-id="f4361-115">特性</span><span class="sxs-lookup"><span data-stu-id="f4361-115">Attribute</span></span>|<span data-ttu-id="f4361-116">描述</span><span class="sxs-lookup"><span data-stu-id="f4361-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f4361-117">activityName</span><span class="sxs-lookup"><span data-stu-id="f4361-117">activityName</span></span>|<span data-ttu-id="f4361-118">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="f4361-118">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|<span data-ttu-id="f4361-119">NAME</span><span class="sxs-lookup"><span data-stu-id="f4361-119">name</span></span>|<span data-ttu-id="f4361-120">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="f4361-120">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4361-121">子元素</span><span class="sxs-lookup"><span data-stu-id="f4361-121">Child Elements</span></span>  
 <span data-ttu-id="f4361-122">无。</span><span class="sxs-lookup"><span data-stu-id="f4361-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4361-123">父元素</span><span class="sxs-lookup"><span data-stu-id="f4361-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f4361-124">元素</span><span class="sxs-lookup"><span data-stu-id="f4361-124">Element</span></span>|<span data-ttu-id="f4361-125">描述</span><span class="sxs-lookup"><span data-stu-id="f4361-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4361-126">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="f4361-126">\<customTrackingQuery></span></span>](customtrackingquery.md)|<span data-ttu-id="f4361-127">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="f4361-127">A query that is used to track events that you define in your code activities.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f4361-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4361-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f4361-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="f4361-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f4361-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="f4361-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
