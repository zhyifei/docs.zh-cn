---
title: "WCF 的 &lt;tracking&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f0b3ad28c5d19ce812b714ef8e2ae92c14ab2a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="lttrackinggt-of-wcf"></a><span data-ttu-id="4df1c-102">WCF 的 &lt;tracking&gt;</span><span class="sxs-lookup"><span data-stu-id="4df1c-102">&lt;tracking&gt; of WCF</span></span>
<span data-ttu-id="4df1c-103">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="4df1c-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="4df1c-104">在工作流跟踪和其配置的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)和[工作流配置跟踪](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="4df1c-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="4df1c-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4df1c-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4df1c-106">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="4df1c-106">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4df1c-107">语法</span><span class="sxs-lookup"><span data-stu-id="4df1c-107">Syntax</span></span>  
  
```xml
   <system.serviceModel>  <tracking>       <participants>       <add name="String"            profileName="String"           type="String" />      </participants>     <trackingProfile name="String">      <workflow activityDefinitionId="String">          <activityScheduledQueries>             <activityScheduledQuery activityName="String"                 childActivityName="String"/>          </activityScheduledQueries>             <activityStateQuery activityName="String" />                <arguments>                   <argument name="String"/>                </arguments>                <states>                   <state name="String"/>                </states>                <variables>                   <variable name="String"/>                </variables>          </activityStateQueries>          <bookmarkResumptionQueries>             <bookmarkResumptionQuery name="String" />          </bookmarkResumptionQueries>          <cancelRequestQueries>             <cancelRequestQuery activityName="String"                 childActivityName="String"/>          </cancelRequestQueries>          <customTrackingQueries>             <customTrackingQuery activityName="String"                 name="String"/>          </customTrackingQueries>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>         <workflowInstanceQueries>            <workflowInstanceQuery>              <states>                 <state name="String"/>              </states>          </workflowInstanceQuery>        </workflowInstanceQueries>      </workflow>    </trackingProfile>           </profiles>  </tracking></system.serviceModel>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4df1c-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4df1c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4df1c-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4df1c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4df1c-110">特性</span><span class="sxs-lookup"><span data-stu-id="4df1c-110">Attributes</span></span>  
 <span data-ttu-id="4df1c-111">无。</span><span class="sxs-lookup"><span data-stu-id="4df1c-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4df1c-112">子元素</span><span class="sxs-lookup"><span data-stu-id="4df1c-112">Child Elements</span></span>  
  
|<span data-ttu-id="4df1c-113">元素</span><span class="sxs-lookup"><span data-stu-id="4df1c-113">Element</span></span>|<span data-ttu-id="4df1c-114">描述</span><span class="sxs-lookup"><span data-stu-id="4df1c-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4df1c-115">\<参与者 ></span><span class="sxs-lookup"><span data-stu-id="4df1c-115">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="4df1c-116">定义参与者的配置元素的集合，这些订阅跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="4df1c-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="4df1c-117">跟踪参与者包含用于处理跟踪记录中负载的逻辑（例如，它们可以选择向某个文件中写入）。</span><span class="sxs-lookup"><span data-stu-id="4df1c-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="4df1c-118">\<trackingProfile ></span><span class="sxs-lookup"><span data-stu-id="4df1c-118">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="4df1c-119">一个跟踪配置文件，用于筛选从工作流实例发出的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="4df1c-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4df1c-120">父元素</span><span class="sxs-lookup"><span data-stu-id="4df1c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4df1c-121">元素</span><span class="sxs-lookup"><span data-stu-id="4df1c-121">Element</span></span>|<span data-ttu-id="4df1c-122">描述</span><span class="sxs-lookup"><span data-stu-id="4df1c-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4df1c-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4df1c-123">system.ServiceModel</span></span>|<span data-ttu-id="4df1c-124">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="4df1c-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4df1c-125">备注</span><span class="sxs-lookup"><span data-stu-id="4df1c-125">Remarks</span></span>  
 <span data-ttu-id="4df1c-126">利用跟踪可以检查工作流的执行。</span><span class="sxs-lookup"><span data-stu-id="4df1c-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="4df1c-127">工作流跟踪基础结构检测工作流以发出反应执行期间关键事件的记录。</span><span class="sxs-lookup"><span data-stu-id="4df1c-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="4df1c-128">例如，工作流实例开始或完成时会发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="4df1c-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="4df1c-129">跟踪还可以提取与工作流变量关联的相关业务数据。</span><span class="sxs-lookup"><span data-stu-id="4df1c-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="4df1c-130">例如，如果工作流表示一个订单处理系统，则可以提取订单 ID 以及跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="4df1c-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="4df1c-131">一般来讲，启用 WF 跟踪便于对工作流的执行进行诊断或业务分析。</span><span class="sxs-lookup"><span data-stu-id="4df1c-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df1c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4df1c-132">See Also</span></span>  
 <span data-ttu-id="4df1c-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4df1c-133"><xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType></span></span>       
 [<span data-ttu-id="4df1c-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="4df1c-134">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
