---
title: <系统.服务模型>工作流
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 9aa2bf0fdfd6fe4528a3fda4d05b3ba8f23637d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151944"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="870e0-102">\<系统.服务模型>工作流</span><span class="sxs-lookup"><span data-stu-id="870e0-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="870e0-103">此配置节包含所有工作流配置元素。</span><span class="sxs-lookup"><span data-stu-id="870e0-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="870e0-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="870e0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="870e0-105">&nbsp;&nbsp;**\<系统。服务模式>**</span><span class="sxs-lookup"><span data-stu-id="870e0-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870e0-106">语法</span><span class="sxs-lookup"><span data-stu-id="870e0-106">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
    <behavior name="String">  
      <bufferReceive maxPendingMessagesPerChannel="Integer" />  
      <etwTracking profileName="String" />  
     <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <channelSettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
        <factorySettings idleTimeout="TimeSpan" leaseTimeout="TimeSpan" maxItemsInCache="Integer" />  
     </sendMessageChannelCache>  
      <sqlWorkflowInstanceStore
          connectionStringName="String"
          hostLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionAction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
    </behavior>  
    </serviceBehaviors>  
  </behaviors>  
  <tracking>
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
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="870e0-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="870e0-107">Attributes and Elements</span></span>  
 <span data-ttu-id="870e0-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="870e0-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="870e0-109">属性</span><span class="sxs-lookup"><span data-stu-id="870e0-109">Attributes</span></span>  
 <span data-ttu-id="870e0-110">无</span><span class="sxs-lookup"><span data-stu-id="870e0-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="870e0-111">子元素</span><span class="sxs-lookup"><span data-stu-id="870e0-111">Child Elements</span></span>  
  
|<span data-ttu-id="870e0-112">元素</span><span class="sxs-lookup"><span data-stu-id="870e0-112">Element</span></span>|<span data-ttu-id="870e0-113">说明</span><span class="sxs-lookup"><span data-stu-id="870e0-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="870e0-114">\<行为></span><span class="sxs-lookup"><span data-stu-id="870e0-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="870e0-115">本节定义**服务行为**集合。</span><span class="sxs-lookup"><span data-stu-id="870e0-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="870e0-116">集合中的每个元素定义服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="870e0-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="870e0-117">每个行为元素都由其唯一**的名称**属性标识。</span><span class="sxs-lookup"><span data-stu-id="870e0-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="870e0-118">\<跟踪></span><span class="sxs-lookup"><span data-stu-id="870e0-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="870e0-119">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="870e0-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="870e0-120">有关工作流跟踪及其配置的详细信息，请参阅工作流[的工作流跟踪和跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)和[配置跟踪](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="870e0-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="870e0-121">父元素</span><span class="sxs-lookup"><span data-stu-id="870e0-121">Parent Elements</span></span>  
  
|<span data-ttu-id="870e0-122">元素</span><span class="sxs-lookup"><span data-stu-id="870e0-122">Element</span></span>|<span data-ttu-id="870e0-123">说明</span><span class="sxs-lookup"><span data-stu-id="870e0-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="870e0-124">\<配置></span><span class="sxs-lookup"><span data-stu-id="870e0-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="870e0-125">.NET 配置文件中的所有配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="870e0-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
