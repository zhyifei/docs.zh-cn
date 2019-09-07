---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: 28d73bb74c4a49052589040adc26194b1300668c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397608"
---
# <a name="tracking"></a><span data-ttu-id="2034e-101">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="2034e-101">\<tracking></span></span>
<span data-ttu-id="2034e-102">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="2034e-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="2034e-103">有关工作流跟踪及其配置的详细信息，请参阅工作流[跟踪和跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)和[配置工作流跟踪](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="2034e-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="2034e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2034e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2034e-105">&nbsp;&nbsp;[ **\<主板.>** ](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="2034e-105">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="2034e-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<跟踪 >**</span><span class="sxs-lookup"><span data-stu-id="2034e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2034e-107">语法</span><span class="sxs-lookup"><span data-stu-id="2034e-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <profiles>
      <participants>
        <add name="String" 
             profileName="String" 
             type="String" />
      </participants>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String" 
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String" />
            </arguments>
            <states>
              <state name="String"  />
            </states>
            <variables>
              <variable name="String" />
            </variables>
          </activityStateQueries>
          <bookmarkResumptionQueries>
            <bookmarkResumptionQuery name="String" />
          </bookmarkResumptionQueries>
          <cancelRequestQueries>
            <cancelRequestQuery activityName="String" 
                                childActivityName="String"/>
          </cancelRequestQueries>
          <customTrackingQueries>
            <customTrackingQuery activityName="String" 
                                 name="String"/>
          </customTrackingQueries>
          <faultPropagationQueries>
            <faultPropagationQuery activityName="String" 
                                   faultHandlerActivityName="String" />
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String" />
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2034e-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2034e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2034e-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2034e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2034e-110">特性</span><span class="sxs-lookup"><span data-stu-id="2034e-110">Attributes</span></span>  
 <span data-ttu-id="2034e-111">无。</span><span class="sxs-lookup"><span data-stu-id="2034e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2034e-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2034e-112">Child Elements</span></span>  
  
|<span data-ttu-id="2034e-113">元素</span><span class="sxs-lookup"><span data-stu-id="2034e-113">Element</span></span>|<span data-ttu-id="2034e-114">描述</span><span class="sxs-lookup"><span data-stu-id="2034e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2034e-115">\<participants></span><span class="sxs-lookup"><span data-stu-id="2034e-115">\<participants></span></span>](participants.md)|<span data-ttu-id="2034e-116">定义订阅跟踪记录的参与者的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="2034e-116">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="2034e-117">跟踪参与者包含用于处理跟踪记录中负载的逻辑（例如，它们可以选择向某个文件中写入）。</span><span class="sxs-lookup"><span data-stu-id="2034e-117">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="2034e-118">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="2034e-118">\<trackingProfile></span></span>](trackingprofile.md)|<span data-ttu-id="2034e-119">一个跟踪配置文件，用于筛选从工作流实例发出的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2034e-119">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2034e-120">父元素</span><span class="sxs-lookup"><span data-stu-id="2034e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2034e-121">元素</span><span class="sxs-lookup"><span data-stu-id="2034e-121">Element</span></span>|<span data-ttu-id="2034e-122">描述</span><span class="sxs-lookup"><span data-stu-id="2034e-122">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2034e-123">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2034e-123">system.ServiceModel</span></span>|<span data-ttu-id="2034e-124">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="2034e-124">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2034e-125">备注</span><span class="sxs-lookup"><span data-stu-id="2034e-125">Remarks</span></span>  
 <span data-ttu-id="2034e-126">利用跟踪可以检查工作流的执行。</span><span class="sxs-lookup"><span data-stu-id="2034e-126">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="2034e-127">工作流跟踪基础结构检测工作流以发出反应执行期间关键事件的记录。</span><span class="sxs-lookup"><span data-stu-id="2034e-127">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="2034e-128">例如，工作流实例开始或完成时会发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2034e-128">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="2034e-129">跟踪还可以提取与工作流变量关联的相关业务数据。</span><span class="sxs-lookup"><span data-stu-id="2034e-129">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="2034e-130">例如，如果工作流表示一个订单处理系统，则可以提取订单 ID 以及跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="2034e-130">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="2034e-131">一般来讲，启用 WF 跟踪便于对工作流的执行进行诊断或业务分析。</span><span class="sxs-lookup"><span data-stu-id="2034e-131">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2034e-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="2034e-132">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="2034e-133">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="2034e-133">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
