---
title: <cancelRequestedQueries>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: eab5af7e-76fa-434d-9d36-873e995cee05
ms.openlocfilehash: 0d08612ce5d74f4f7f505c538187ddecea610132
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398825"
---
# <a name="cancelrequestedqueries"></a><span data-ttu-id="30af0-101">\<cancelRequestedQueries></span><span class="sxs-lookup"><span data-stu-id="30af0-101">\<cancelRequestedQueries></span></span>
<span data-ttu-id="30af0-102">表示一个查询集合，这些查询用于跟踪父活动取消子活动的请求。</span><span class="sxs-lookup"><span data-stu-id="30af0-102">Represents a collection of queries that are used to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="30af0-103">跟踪参与者需要用此查询来订阅取消请求记录对象。</span><span class="sxs-lookup"><span data-stu-id="30af0-103">The query is necessary for a tracking participant to subscribe to cancel request record objects.</span></span>  
  
 <span data-ttu-id="30af0-104">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="30af0-104">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md)</span></span>  
  
<span data-ttu-id="30af0-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="30af0-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="30af0-106">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="30af0-106">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="30af0-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking.md)</span><span class="sxs-lookup"><span data-stu-id="30af0-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)</span></span>\
<span data-ttu-id="30af0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile.md)</span><span class="sxs-lookup"><span data-stu-id="30af0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)</span></span>\
<span data-ttu-id="30af0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow.md)</span><span class="sxs-lookup"><span data-stu-id="30af0-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)</span></span>\
<span data-ttu-id="30af0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<q >**</span><span class="sxs-lookup"><span data-stu-id="30af0-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cancelRequestedQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30af0-111">语法</span><span class="sxs-lookup"><span data-stu-id="30af0-111">Syntax</span></span>  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <cancelRequestQueries>
        <cancelRequestQuery activityName="String" 
                            childActivityName="String"/>
      </cancelRequestQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30af0-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="30af0-112">Attributes and Elements</span></span>  
 <span data-ttu-id="30af0-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="30af0-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30af0-114">特性</span><span class="sxs-lookup"><span data-stu-id="30af0-114">Attributes</span></span>  
 <span data-ttu-id="30af0-115">无。</span><span class="sxs-lookup"><span data-stu-id="30af0-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="30af0-116">子元素</span><span class="sxs-lookup"><span data-stu-id="30af0-116">Child Elements</span></span>  
  
|<span data-ttu-id="30af0-117">元素</span><span class="sxs-lookup"><span data-stu-id="30af0-117">Element</span></span>|<span data-ttu-id="30af0-118">描述</span><span class="sxs-lookup"><span data-stu-id="30af0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30af0-119">\<cancelRequestedQuery></span><span class="sxs-lookup"><span data-stu-id="30af0-119">\<cancelRequestedQuery></span></span>](cancelrequestedquery.md)|<span data-ttu-id="30af0-120">一个查询，用于跟踪父活动取消子活动的请求</span><span class="sxs-lookup"><span data-stu-id="30af0-120">A query that is used to track requests to cancel a child activity by the parent activity</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="30af0-121">父元素</span><span class="sxs-lookup"><span data-stu-id="30af0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="30af0-122">元素</span><span class="sxs-lookup"><span data-stu-id="30af0-122">Element</span></span>|<span data-ttu-id="30af0-123">描述</span><span class="sxs-lookup"><span data-stu-id="30af0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30af0-124">\<workflow></span><span class="sxs-lookup"><span data-stu-id="30af0-124">\<workflow></span></span>](workflow.md)|<span data-ttu-id="30af0-125">一个配置元素，该元素包含由**activityDefinitionId**属性标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="30af0-125">A configuration element that contains all queries for a specific workflow identified by the **activityDefinitionId** property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30af0-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="30af0-126">See also</span></span>

- [<span data-ttu-id="30af0-127">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="30af0-127">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="30af0-128">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="30af0-128">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
