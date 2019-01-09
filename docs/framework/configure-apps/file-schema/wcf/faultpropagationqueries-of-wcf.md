---
title: WCF 的 &lt;faultPropagationQueries&gt;
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 77a38f8474b5e2ac8634d6ea91bc80c6044ff3ed
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54144959"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a><span data-ttu-id="f094b-102">WCF 的 &lt;faultPropagationQueries&gt;</span><span class="sxs-lookup"><span data-stu-id="f094b-102">&lt;faultPropagationQueries&gt; of WCF</span></span>

<span data-ttu-id="f094b-103">表示一个查询集合，这些查询用于跟踪在某个活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="f094b-103">Represents a collection of queries that are used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f094b-104">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="f094b-104">This event occurs each time a FaultHandler processes a fault.</span></span> <span data-ttu-id="f094b-105">应使用此类查询来跟踪对在活动中出现的错误进行的处理。</span><span class="sxs-lookup"><span data-stu-id="f094b-105">You should use such query to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f094b-106">跟踪参与者需要用此查询来订阅错误传播记录。</span><span class="sxs-lookup"><span data-stu-id="f094b-106">The query is necessary for a  tracking participant to subscribe to fault propagation records.</span></span>  
  
<span data-ttu-id="f094b-107">有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="f094b-107">For more information on tracking profile queries, see [Tracking Profiles](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
<span data-ttu-id="f094b-108">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f094b-108">\<system.serviceModel></span></span>  
<span data-ttu-id="f094b-109">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="f094b-109">\<tracking></span></span>  
<span data-ttu-id="f094b-110">\<配置文件 ></span><span class="sxs-lookup"><span data-stu-id="f094b-110">\<profiles></span></span>  
<span data-ttu-id="f094b-111">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="f094b-111">\<trackingProfile></span></span>  
<span data-ttu-id="f094b-112">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="f094b-112">\<workflow></span></span>  
<span data-ttu-id="f094b-113">\<faultPropagationQueries ></span><span class="sxs-lookup"><span data-stu-id="f094b-113">\<faultPropagationQueries></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f094b-114">语法</span><span class="sxs-lookup"><span data-stu-id="f094b-114">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f094b-115">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f094b-115">Attributes and elements</span></span>

<span data-ttu-id="f094b-116">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f094b-116">The following sections describe attributes, child elements, and parent elements.</span></span>
  
### <a name="attributes"></a><span data-ttu-id="f094b-117">特性</span><span class="sxs-lookup"><span data-stu-id="f094b-117">Attributes</span></span>

<span data-ttu-id="f094b-118">无。</span><span class="sxs-lookup"><span data-stu-id="f094b-118">None.</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f094b-119">子元素</span><span class="sxs-lookup"><span data-stu-id="f094b-119">Child elements</span></span>

|<span data-ttu-id="f094b-120">元素</span><span class="sxs-lookup"><span data-stu-id="f094b-120">Element</span></span>|<span data-ttu-id="f094b-121">描述</span><span class="sxs-lookup"><span data-stu-id="f094b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f094b-122">\<faultPropagationQuery ></span><span class="sxs-lookup"><span data-stu-id="f094b-122">\<faultPropagationQuery></span></span>](faultpropagationquery-of-wcf.md)|<span data-ttu-id="f094b-123">一个查询，用于跟踪在活动中发生的错误的处理。</span><span class="sxs-lookup"><span data-stu-id="f094b-123">A query that is used to track the handling of faults that occur within an activity.</span></span>  <span data-ttu-id="f094b-124">每次 FaultHandler 处理错误时，都会发生此事件。</span><span class="sxs-lookup"><span data-stu-id="f094b-124">This event occurs each time a FaultHandler processes a fault.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f094b-125">父元素</span><span class="sxs-lookup"><span data-stu-id="f094b-125">Parent elements</span></span>  
  
|<span data-ttu-id="f094b-126">元素</span><span class="sxs-lookup"><span data-stu-id="f094b-126">Element</span></span>|<span data-ttu-id="f094b-127">描述</span><span class="sxs-lookup"><span data-stu-id="f094b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f094b-128">\<工作流 ></span><span class="sxs-lookup"><span data-stu-id="f094b-128">\<workflow></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|<span data-ttu-id="f094b-129">一个配置元素，包含 `activityDefinitionId` 属性所标识的特定工作流的所有查询。</span><span class="sxs-lookup"><span data-stu-id="f094b-129">A configuration element that contains all queries for a specific workflow identified by the `activityDefinitionId` property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f094b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="f094b-130">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [<span data-ttu-id="f094b-131">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="f094b-131">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="f094b-132">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="f094b-132">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
