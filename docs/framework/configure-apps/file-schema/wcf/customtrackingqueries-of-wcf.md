---
title: <customTrackingQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: 14cfe47e-9935-4120-84f1-8f38de8ca4c1
ms.openlocfilehash: 2c4bd74ae346c536e8bc0ae454e638b7c76a40fc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855434"
---
# <a name="customtrackingqueries-of-wcf"></a><span data-ttu-id="9b763-102">\<WCF 的 q ></span><span class="sxs-lookup"><span data-stu-id="9b763-102">\<customTrackingQueries> of WCF</span></span>

<span data-ttu-id="9b763-103">表示一个查询集合，这些查询用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="9b763-103">Represents a collection of queries that are used to track events that you define in your code activities.</span></span> <span data-ttu-id="9b763-104">跟踪参与者需要用此查询来订阅自定义跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="9b763-104">The query is necessary for a tracking participant to subscribe to custom tracking records.</span></span>  
  
<span data-ttu-id="9b763-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="9b763-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>
  
<span data-ttu-id="9b763-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9b763-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9b763-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9b763-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9b763-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9b763-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="9b763-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="9b763-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="9b763-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9b763-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="9b763-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="9b763-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="9b763-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<q >**</span><span class="sxs-lookup"><span data-stu-id="9b763-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customTrackingQueries>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="9b763-113">语法</span><span class="sxs-lookup"><span data-stu-id="9b763-113">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b763-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9b763-114">Attributes and elements</span></span>

<span data-ttu-id="9b763-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9b763-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b763-116">特性</span><span class="sxs-lookup"><span data-stu-id="9b763-116">Attributes</span></span>

<span data-ttu-id="9b763-117">无。</span><span class="sxs-lookup"><span data-stu-id="9b763-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="9b763-118">子元素</span><span class="sxs-lookup"><span data-stu-id="9b763-118">Child elements</span></span>
  
|<span data-ttu-id="9b763-119">元素</span><span class="sxs-lookup"><span data-stu-id="9b763-119">Element</span></span>|<span data-ttu-id="9b763-120">描述</span><span class="sxs-lookup"><span data-stu-id="9b763-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b763-121">\<customTrackingQuery></span><span class="sxs-lookup"><span data-stu-id="9b763-121">\<customTrackingQuery></span></span>](customtrackingquery-of-wcf.md)|<span data-ttu-id="9b763-122">一个查询，用于跟踪你在代码活动中定义的事件。</span><span class="sxs-lookup"><span data-stu-id="9b763-122">A query that is used to track events that you define in your code activities.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9b763-123">父元素</span><span class="sxs-lookup"><span data-stu-id="9b763-123">Parent elements</span></span>  
  
|<span data-ttu-id="9b763-124">元素</span><span class="sxs-lookup"><span data-stu-id="9b763-124">Element</span></span>|<span data-ttu-id="9b763-125">描述</span><span class="sxs-lookup"><span data-stu-id="9b763-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9b763-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="9b763-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="9b763-127">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="9b763-127">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9b763-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b763-128">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [<span data-ttu-id="9b763-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="9b763-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="9b763-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="9b763-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
