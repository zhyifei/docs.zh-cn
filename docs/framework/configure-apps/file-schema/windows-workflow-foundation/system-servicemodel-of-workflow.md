---
title: 工作流的 &lt;system.serviceModel&gt;
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 62047d68d559a34ead290cf18f77d032841210b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemservicemodelgt-of-workflow"></a><span data-ttu-id="1d1e7-102">工作流的 &lt;system.serviceModel&gt;</span><span class="sxs-lookup"><span data-stu-id="1d1e7-102">&lt;system.serviceModel&gt; of workflow</span></span>
<span data-ttu-id="1d1e7-103">此配置节包含所有工作流配置元素。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d1e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d1e7-104">Syntax</span></span>  
  
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
          honstLockRenewalPeriod="TimeSpan"  
          instanceCompletionAction="DeleteNothing/DeleteAll"  
          instanceEncodingAction="None/GZip"  
          instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry"  
          runnableInstancesDetectionPeriod="TimeSpan" />  
      <workflowIdle timeToPersist="TimeSpan"  
          timeToUnload="TimeSpan" />  
      <workflowUnhandledExceptionaction="Abandon/AbandonAndSuspend/Cancel/Terminate" />  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d1e7-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1d1e7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="1d1e7-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d1e7-107">特性</span><span class="sxs-lookup"><span data-stu-id="1d1e7-107">Attributes</span></span>  
 <span data-ttu-id="1d1e7-108">无</span><span class="sxs-lookup"><span data-stu-id="1d1e7-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1d1e7-109">子元素</span><span class="sxs-lookup"><span data-stu-id="1d1e7-109">Child Elements</span></span>  
  
|<span data-ttu-id="1d1e7-110">元素</span><span class="sxs-lookup"><span data-stu-id="1d1e7-110">Element</span></span>|<span data-ttu-id="1d1e7-111">描述</span><span class="sxs-lookup"><span data-stu-id="1d1e7-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d1e7-112">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="1d1e7-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="1d1e7-113">本部分定义**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="1d1e7-114">集合中的每个元素定义服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="1d1e7-115">每个行为元素由其唯一标识**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="1d1e7-116">\<跟踪 ></span><span class="sxs-lookup"><span data-stu-id="1d1e7-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="1d1e7-117">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="1d1e7-118">在工作流跟踪和其配置的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)和[工作流配置跟踪](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d1e7-119">父元素</span><span class="sxs-lookup"><span data-stu-id="1d1e7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1d1e7-120">元素</span><span class="sxs-lookup"><span data-stu-id="1d1e7-120">Element</span></span>|<span data-ttu-id="1d1e7-121">描述</span><span class="sxs-lookup"><span data-stu-id="1d1e7-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1d1e7-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1d1e7-122">\<configuration></span></span>|<span data-ttu-id="1d1e7-123">.NET 配置文件中的所有配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="1d1e7-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
