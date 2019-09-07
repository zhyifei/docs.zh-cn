---
title: <tracking>WCF 的
ms.date: 03/30/2017
ms.assetid: 70cfaf24-a91c-4e56-ac47-d2ed87a963b3
ms.openlocfilehash: e8f74d635299a965b754536234e6be28e4e7a104
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399423"
---
# <a name="tracking-of-wcf"></a><span data-ttu-id="0b37c-102">\<跟踪 WCF ></span><span class="sxs-lookup"><span data-stu-id="0b37c-102">\<tracking> of WCF</span></span>
<span data-ttu-id="0b37c-103">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="0b37c-103">Represents a configuration section for defining tracking settings for a workflow service.</span></span>  
  
 <span data-ttu-id="0b37c-104">有关工作流跟踪及其配置的详细信息，请参阅工作流[跟踪和跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)和[配置工作流跟踪](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="0b37c-104">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
<span data-ttu-id="0b37c-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0b37c-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0b37c-106">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0b37c-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0b37c-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<跟踪 >**</span><span class="sxs-lookup"><span data-stu-id="0b37c-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<tracking>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b37c-108">语法</span><span class="sxs-lookup"><span data-stu-id="0b37c-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <tracking>
    <participants>
      <add name="String"
           profileName="String"
           type="String" />
    </participants>
    <profiles>
      <trackingProfile name="String">
        <workflow activityDefinitionId="String">
          <activityScheduledQueries>
            <activityScheduledQuery activityName="String"
                                    childActivityName="String"/>
          </activityScheduledQueries>
          <activityStateQueries>
            <activityStateQuery activityName="String" />
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
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
                                   faultHandlerActivityName="String"/>
          </faultPropagationQueries>
          <workflowInstanceQueries>
            <workflowInstanceQuery>
              <states>
                <state name="String"/>
              </states>
            </workflowInstanceQuery>
          </workflowInstanceQueries>
        </workflow>
      </trackingProfile>
    </profiles>
  </tracking>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b37c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0b37c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="0b37c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0b37c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b37c-111">特性</span><span class="sxs-lookup"><span data-stu-id="0b37c-111">Attributes</span></span>  
 <span data-ttu-id="0b37c-112">无。</span><span class="sxs-lookup"><span data-stu-id="0b37c-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b37c-113">子元素</span><span class="sxs-lookup"><span data-stu-id="0b37c-113">Child Elements</span></span>  
  
|<span data-ttu-id="0b37c-114">元素</span><span class="sxs-lookup"><span data-stu-id="0b37c-114">Element</span></span>|<span data-ttu-id="0b37c-115">描述</span><span class="sxs-lookup"><span data-stu-id="0b37c-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b37c-116">\<participants></span><span class="sxs-lookup"><span data-stu-id="0b37c-116">\<participants></span></span>](../windows-workflow-foundation/participants.md)|<span data-ttu-id="0b37c-117">定义订阅跟踪记录的参与者的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="0b37c-117">A collection of configuration elements defining participants that subscribe to tracking records.</span></span> <span data-ttu-id="0b37c-118">跟踪参与者包含用于处理跟踪记录中负载的逻辑（例如，它们可以选择向某个文件中写入）。</span><span class="sxs-lookup"><span data-stu-id="0b37c-118">The tracking participants contain the logic to process the payload from the tracking records (for example, they could choose to write to a file).</span></span>|  
|[<span data-ttu-id="0b37c-119">\<trackingProfile></span><span class="sxs-lookup"><span data-stu-id="0b37c-119">\<trackingProfile></span></span>](../windows-workflow-foundation/trackingprofile.md)|<span data-ttu-id="0b37c-120">一个跟踪配置文件，用于筛选从工作流实例发出的跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="0b37c-120">A tracking profile to filter tracking records emitted from a workflow instance.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b37c-121">父元素</span><span class="sxs-lookup"><span data-stu-id="0b37c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="0b37c-122">元素</span><span class="sxs-lookup"><span data-stu-id="0b37c-122">Element</span></span>|<span data-ttu-id="0b37c-123">描述</span><span class="sxs-lookup"><span data-stu-id="0b37c-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0b37c-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0b37c-124">system.ServiceModel</span></span>|<span data-ttu-id="0b37c-125">所有工作流配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="0b37c-125">The root element of all workflow configuration elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b37c-126">备注</span><span class="sxs-lookup"><span data-stu-id="0b37c-126">Remarks</span></span>  
 <span data-ttu-id="0b37c-127">利用跟踪可以检查工作流的执行。</span><span class="sxs-lookup"><span data-stu-id="0b37c-127">Tracking provides you with the ability to examine the execution of a workflow.</span></span> <span data-ttu-id="0b37c-128">工作流跟踪基础结构检测工作流以发出反应执行期间关键事件的记录。</span><span class="sxs-lookup"><span data-stu-id="0b37c-128">The workflow tracking infrastructure instruments a workflow to emit records reflecting key events during the execution.</span></span> <span data-ttu-id="0b37c-129">例如，工作流实例开始或完成时会发出跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="0b37c-129">For example, when a workflow instance starts or completes tracking records are emitted.</span></span> <span data-ttu-id="0b37c-130">跟踪还可以提取与工作流变量关联的相关业务数据。</span><span class="sxs-lookup"><span data-stu-id="0b37c-130">Tracking can also extract business relevant data associated with the workflow variables.</span></span> <span data-ttu-id="0b37c-131">例如，如果工作流表示一个订单处理系统，则可以提取订单 ID 以及跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="0b37c-131">For example, if the workflow represents an order processing system the order id can be extracted along with the tracking record.</span></span> <span data-ttu-id="0b37c-132">一般来讲，启用 WF 跟踪便于对工作流的执行进行诊断或业务分析。</span><span class="sxs-lookup"><span data-stu-id="0b37c-132">In general, enabling WF tracking facilitates diagnostics or business analytics over a workflow execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b37c-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b37c-133">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.TrackingSection?displayProperty=nameWithType>
- [<span data-ttu-id="0b37c-134">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="0b37c-134">Workflow Tracking and Tracing</span></span>](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
