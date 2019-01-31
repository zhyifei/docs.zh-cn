---
title: 工作流的 <system.serviceModel>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 005a274df9e9ab99227a3748b7a25c9d465d020f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271119"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="ee0df-102">\<system.serviceModel > 的工作流</span><span class="sxs-lookup"><span data-stu-id="ee0df-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="ee0df-103">此配置节包含所有工作流配置元素。</span><span class="sxs-lookup"><span data-stu-id="ee0df-103">This configuration section contains all the workflow configuration elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0df-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee0df-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee0df-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ee0df-105">Attributes and Elements</span></span>  
 <span data-ttu-id="ee0df-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ee0df-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee0df-107">特性</span><span class="sxs-lookup"><span data-stu-id="ee0df-107">Attributes</span></span>  
 <span data-ttu-id="ee0df-108">无</span><span class="sxs-lookup"><span data-stu-id="ee0df-108">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ee0df-109">子元素</span><span class="sxs-lookup"><span data-stu-id="ee0df-109">Child Elements</span></span>  
  
|<span data-ttu-id="ee0df-110">元素</span><span class="sxs-lookup"><span data-stu-id="ee0df-110">Element</span></span>|<span data-ttu-id="ee0df-111">描述</span><span class="sxs-lookup"><span data-stu-id="ee0df-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee0df-112">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="ee0df-112">\<behaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behaviors-of-workflow.md)|<span data-ttu-id="ee0df-113">本部分将定义**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="ee0df-113">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="ee0df-114">集合中的每个元素定义服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="ee0df-114">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="ee0df-115">每个行为元素由其唯一**名称**属性。</span><span class="sxs-lookup"><span data-stu-id="ee0df-115">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="ee0df-116">\<tracking></span><span class="sxs-lookup"><span data-stu-id="ee0df-116">\<tracking></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|<span data-ttu-id="ee0df-117">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="ee0df-117">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="ee0df-118">工作流跟踪和其配置的详细信息，请参阅[工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)并[工作流配置跟踪](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="ee0df-118">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee0df-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ee0df-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ee0df-120">元素</span><span class="sxs-lookup"><span data-stu-id="ee0df-120">Element</span></span>|<span data-ttu-id="ee0df-121">描述</span><span class="sxs-lookup"><span data-stu-id="ee0df-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ee0df-122">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ee0df-122">\<configuration></span></span>|<span data-ttu-id="ee0df-123">.NET 配置文件中的所有配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="ee0df-123">The root element for all configuration elements in a .NET configuration file.</span></span>|
