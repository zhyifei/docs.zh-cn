---
title: <faultPropagationQueries>WCF 的
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 709c2c6907b4d0d28118f9de12edb047aa16d741
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855266"
---
# <a name="faultpropagationqueries-of-wcf"></a><span data-ttu-id="f06eb-102">\<WCF 的 faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="f06eb-102">\<faultPropagationQueries> of WCF</span></span>

<span data-ttu-id="f06eb-103">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="f06eb-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f06eb-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="f06eb-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f06eb-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="f06eb-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f06eb-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="f06eb-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="f06eb-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="f06eb-107">For more information on tracking profile queries, see [Tracking Profiles](../../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f06eb-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f06eb-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f06eb-109">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f06eb-109">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f06eb-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<跟踪 >** ](tracking-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f06eb-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking-of-wcf.md)</span></span>\
<span data-ttu-id="f06eb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<配置文件 >** </span><span class="sxs-lookup"><span data-stu-id="f06eb-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<profiles>**</span></span>\
<span data-ttu-id="f06eb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Trackingprofile&gt >** ](trackingprofile-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f06eb-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile-of-wcf.md)</span></span>\
<span data-ttu-id="f06eb-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<工作流 >** ](workflow-of-wcf.md)</span><span class="sxs-lookup"><span data-stu-id="f06eb-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow-of-wcf.md)</span></span>\
<span data-ttu-id="f06eb-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<faultPropagationQueries >**</span><span class="sxs-lookup"><span data-stu-id="f06eb-114">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQueries>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06eb-115">语法</span><span class="sxs-lookup"><span data-stu-id="f06eb-115">Syntax</span></span>  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f06eb-116">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f06eb-116">Attributes and elements</span></span>

<span data-ttu-id="f06eb-117">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f06eb-117">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f06eb-118">特性</span><span class="sxs-lookup"><span data-stu-id="f06eb-118">Attributes</span></span>

<span data-ttu-id="f06eb-119">无。</span><span class="sxs-lookup"><span data-stu-id="f06eb-119">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f06eb-120">子元素</span><span class="sxs-lookup"><span data-stu-id="f06eb-120">Child elements</span></span>

|<span data-ttu-id="f06eb-121">元素</span><span class="sxs-lookup"><span data-stu-id="f06eb-121">Element</span></span>|<span data-ttu-id="f06eb-122">描述</span><span class="sxs-lookup"><span data-stu-id="f06eb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f06eb-123">\<faultPropagationQuery></span><span class="sxs-lookup"><span data-stu-id="f06eb-123">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="f06eb-124">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="f06eb-124">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f06eb-125">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="f06eb-125">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f06eb-126">父元素</span><span class="sxs-lookup"><span data-stu-id="f06eb-126">Parent elements</span></span>  
  
|<span data-ttu-id="f06eb-127">元素</span><span class="sxs-lookup"><span data-stu-id="f06eb-127">Element</span></span>|<span data-ttu-id="f06eb-128">描述</span><span class="sxs-lookup"><span data-stu-id="f06eb-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f06eb-129">\<workflow></span><span class="sxs-lookup"><span data-stu-id="f06eb-129">\<workflow></span></span>](../windows-workflow-foundation/workflow.md)|<span data-ttu-id="f06eb-130">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="f06eb-130">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f06eb-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f06eb-131">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f06eb-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="f06eb-132">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f06eb-133">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="f06eb-133">Tracking Profiles</span></span>](../../../windows-workflow-foundation/tracking-profiles.md)
