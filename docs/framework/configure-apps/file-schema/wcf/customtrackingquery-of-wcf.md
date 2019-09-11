---
title: <customTrackingQuery>WCF 的
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: 204bbb6cf5ebcb30bf92b697885ecbbbd94385e0
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855421"
---
# <a name="customtrackingquery-of-wcf"></a><span data-ttu-id="eaa72-102">\<WCF 的 customTrackingQuery ></span><span class="sxs-lookup"><span data-stu-id="eaa72-102">\<customTrackingQuery> of WCF</span></span>

<span data-ttu-id="eaa72-103">表示一个查询，该查询用于跟踪您在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="eaa72-103">Represents a query that is used to track events that you define in your code activities.</span></span> <span data-ttu-id="eaa72-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="eaa72-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>

<span data-ttu-id="eaa72-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="eaa72-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eaa72-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eaa72-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="eaa72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="eaa72-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="eaa72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="eaa72-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="eaa72-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<q >** ](customtrackingqueries-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="eaa72-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customTrackingQueries>**](customtrackingqueries-of-wcf.md)</span></span>\
<span data-ttu-id="eaa72-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customTrackingQuery >**</span><span class="sxs-lookup"><span data-stu-id="eaa72-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQuery>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaa72-114">语法</span><span class="sxs-lookup"><span data-stu-id="eaa72-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eaa72-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="eaa72-115">Attributes and elements</span></span>  

<span data-ttu-id="eaa72-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="eaa72-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eaa72-117">特性</span><span class="sxs-lookup"><span data-stu-id="eaa72-117">Attributes</span></span>  
  
|<span data-ttu-id="eaa72-118">特性</span><span class="sxs-lookup"><span data-stu-id="eaa72-118">Attribute</span></span>|<span data-ttu-id="eaa72-119">描述</span><span class="sxs-lookup"><span data-stu-id="eaa72-119">Description</span></span>|  
|---------------|-----------------|  
|`activityName`|<span data-ttu-id="eaa72-120">一个字符串，指定生成跟踪记录的活动的名称。</span><span class="sxs-lookup"><span data-stu-id="eaa72-120">A string that specifies the name of the activity that generated the tracking record.</span></span>|  
|`name`|<span data-ttu-id="eaa72-121">一个字符串，指定发出的自定义跟踪记录的名称。</span><span class="sxs-lookup"><span data-stu-id="eaa72-121">A string that specifies the name of the custom tracking record that is emitted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eaa72-122">子元素</span><span class="sxs-lookup"><span data-stu-id="eaa72-122">Child elements</span></span>

<span data-ttu-id="eaa72-123">无。</span><span class="sxs-lookup"><span data-stu-id="eaa72-123">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="eaa72-124">父元素</span><span class="sxs-lookup"><span data-stu-id="eaa72-124">Parent elements</span></span>

|<span data-ttu-id="eaa72-125">元素</span><span class="sxs-lookup"><span data-stu-id="eaa72-125">Element</span></span>|<span data-ttu-id="eaa72-126">描述</span><span class="sxs-lookup"><span data-stu-id="eaa72-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eaa72-127">\<customTrackingQueries></span><span class="sxs-lookup"><span data-stu-id="eaa72-127">\<customTrackingQueries></span></span>](customtrackingqueries-of-wcf.md)|<span data-ttu-id="eaa72-128">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="eaa72-128">Represents a collection of queries that are used to track events that you define in your code activities.</span></span>|
  
## <a name="see-also"></a><span data-ttu-id="eaa72-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaa72-129">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="eaa72-130">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="eaa72-130">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="eaa72-131">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="eaa72-131">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
