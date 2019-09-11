---
title: <cancelRequestedQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: a7cc7125-9ea3-4d3f-99c0-878cdeb1258a
ms.openlocfilehash: 63cfc835ac7ce88bde56fd9243a2cf6652cbce6e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850094"
---
# <a name="cancelrequestedqueries-of-wcf"></a><span data-ttu-id="b3127-102">\<WCF 的 q ></span><span class="sxs-lookup"><span data-stu-id="b3127-102">\<cancelRequestedQueries> of WCF</span></span>
<span data-ttu-id="b3127-103">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="b3127-103">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="b3127-104">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="b3127-104">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
<span data-ttu-id="b3127-105">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="b3127-105">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="b3127-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b3127-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b3127-107">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b3127-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b3127-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b3127-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="b3127-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="b3127-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="b3127-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b3127-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="b3127-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="b3127-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="b3127-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<q >**</span><span class="sxs-lookup"><span data-stu-id="b3127-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3127-113">语法</span><span class="sxs-lookup"><span data-stu-id="b3127-113">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <cancelRequestQueries>
          <cancelRequestQuery activityName="String"
                              childActivityName="String" />
        </cancelRequestQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3127-114">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b3127-114">Attributes and elements</span></span>  

<span data-ttu-id="b3127-115">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b3127-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3127-116">特性</span><span class="sxs-lookup"><span data-stu-id="b3127-116">Attributes</span></span>

<span data-ttu-id="b3127-117">无。</span><span class="sxs-lookup"><span data-stu-id="b3127-117">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="b3127-118">子元素</span><span class="sxs-lookup"><span data-stu-id="b3127-118">Child elements</span></span>
  
|<span data-ttu-id="b3127-119">元素</span><span class="sxs-lookup"><span data-stu-id="b3127-119">Element</span></span>|<span data-ttu-id="b3127-120">描述</span><span class="sxs-lookup"><span data-stu-id="b3127-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3127-121">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="b3127-121">\<cancelRequestedQuery></span></span>](cancelrequestedquery-of-wcf.md)|<span data-ttu-id="b3127-122">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="b3127-122">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b3127-123">父元素</span><span class="sxs-lookup"><span data-stu-id="b3127-123">Parent elements</span></span>  
  
|<span data-ttu-id="b3127-124">元素</span><span class="sxs-lookup"><span data-stu-id="b3127-124">Element</span></span>|<span data-ttu-id="b3127-125">描述</span><span class="sxs-lookup"><span data-stu-id="b3127-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3127-126">\<workflow></span><span class="sxs-lookup"><span data-stu-id="b3127-126">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="b3127-127">一个配置元素，包含 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="b3127-127">A configuration element that contains all queries for a specific workflow identified by the <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement.ActivityDefinitionId> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b3127-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3127-128">See also</span></span>

- <xref:System.Activities.Tracking.CancelRequestedQuery>
- [<span data-ttu-id="b3127-129">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="b3127-129">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="b3127-130">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="b3127-130">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
