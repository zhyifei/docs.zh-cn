---
title: <tracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: fd9b50ed-98a1-4518-836d-e4e02c670822
ms.openlocfilehash: fa96cb374204ffbdb4c0fcd353c70b6e27ef7481
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263805"
---
# <a name="tracking"></a><span data-ttu-id="37538-101">\<tracking></span><span class="sxs-lookup"><span data-stu-id="37538-101">\<tracking></span></span>
<span data-ttu-id="37538-102">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="37538-102">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="37538-103">工作流跟踪和其配置的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)并[工作流配置跟踪](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="37538-103">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="37538-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="37538-104">\<system.serviceModel></span></span>  
<span data-ttu-id="37538-105">\<tracking></span><span class="sxs-lookup"><span data-stu-id="37538-105">\<tracking></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37538-106">语法</span><span class="sxs-lookup"><span data-stu-id="37538-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="37538-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="37538-107">Attributes and Elements</span></span>  
 <span data-ttu-id="37538-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="37538-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="37538-109">特性</span><span class="sxs-lookup"><span data-stu-id="37538-109">Attributes</span></span>  
 <span data-ttu-id="37538-110">无。</span><span class="sxs-lookup"><span data-stu-id="37538-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="37538-111">子元素</span><span class="sxs-lookup"><span data-stu-id="37538-111">Child Elements</span></span>  
  
|<span data-ttu-id="37538-112">元素</span><span class="sxs-lookup"><span data-stu-id="37538-112">Element</span></span>|<span data-ttu-id="37538-113">描述</span><span class="sxs-lookup"><span data-stu-id="37538-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37538-114">\<participants></span><span class="sxs-lookup"><span data-stu-id="37538-114">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|<span data-ttu-id="37538-115">定义参与方的配置元素的集合的订阅跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="37538-115">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="37538-116">跟踪参与者包含用于处理跟踪记录中负载的逻辑（例如，它们可以选择向某个文件中写入）。</span><span class="sxs-lookup"><span data-stu-id="37538-116">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="37538-117">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="37538-117">\<trackingProfile></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="37538-118">一个跟踪配置文件，用于筛选从工作流实例发出的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="37538-118">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="37538-119">父元素</span><span class="sxs-lookup"><span data-stu-id="37538-119">Parent Elements</span></span>  
  
|<span data-ttu-id="37538-120">元素</span><span class="sxs-lookup"><span data-stu-id="37538-120">Element</span></span>|<span data-ttu-id="37538-121">描述</span><span class="sxs-lookup"><span data-stu-id="37538-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37538-122">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="37538-122">system.ServiceModel</span></span>|<span data-ttu-id="37538-123">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="37538-123">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="37538-124">备注</span><span class="sxs-lookup"><span data-stu-id="37538-124">Remarks</span></span>  
 <span data-ttu-id="37538-125">利用跟踪可以检查工作流的执行。</span><span class="sxs-lookup"><span data-stu-id="37538-125">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="37538-126">工作流跟踪基础结构检测工作流以发出反应执行期间关键事件的记录。</span><span class="sxs-lookup"><span data-stu-id="37538-126">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="37538-127">例如，工作流实例开始或完成时会发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="37538-127">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="37538-128">跟踪还可以提取与工作流变量关联的相关业务数据。</span><span class="sxs-lookup"><span data-stu-id="37538-128">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="37538-129">例如，如果工作流表示一个订单处理系统，则可以提取订单 ID 以及跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="37538-129">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="37538-130">一般来讲，启用 WF 跟踪便于对工作流的执行进行诊断或业务分析。</span><span class="sxs-lookup"><span data-stu-id="37538-130">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37538-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="37538-131">See also</span></span>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="37538-132">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="37538-132">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
