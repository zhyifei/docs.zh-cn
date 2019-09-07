---
title: < System.servicemodel > 工作流
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a8eb2bf-f925-40e1-ba5c-a49b1d3a3ac6
ms.openlocfilehash: 757a7a132a6e765e257097d251a110297c6a40bf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398603"
---
# <a name="systemservicemodel-of-workflow"></a><span data-ttu-id="53f1a-102">\<工作流的 System.servicemodel ></span><span class="sxs-lookup"><span data-stu-id="53f1a-102">\<system.serviceModel> of workflow</span></span>
<span data-ttu-id="53f1a-103">此配置节包含所有工作流配置元素。</span><span class="sxs-lookup"><span data-stu-id="53f1a-103">This configuration section contains all the workflow configuration elements.</span></span>  

<span data-ttu-id="53f1a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="53f1a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="53f1a-105">&nbsp;&nbsp; **\<主板.>**</span><span class="sxs-lookup"><span data-stu-id="53f1a-105">&nbsp;&nbsp;**\<system.ServiceModel>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53f1a-106">语法</span><span class="sxs-lookup"><span data-stu-id="53f1a-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="53f1a-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="53f1a-107">Attributes and Elements</span></span>  
 <span data-ttu-id="53f1a-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="53f1a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="53f1a-109">特性</span><span class="sxs-lookup"><span data-stu-id="53f1a-109">Attributes</span></span>  
 <span data-ttu-id="53f1a-110">无</span><span class="sxs-lookup"><span data-stu-id="53f1a-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="53f1a-111">子元素</span><span class="sxs-lookup"><span data-stu-id="53f1a-111">Child Elements</span></span>  
  
|<span data-ttu-id="53f1a-112">元素</span><span class="sxs-lookup"><span data-stu-id="53f1a-112">Element</span></span>|<span data-ttu-id="53f1a-113">描述</span><span class="sxs-lookup"><span data-stu-id="53f1a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53f1a-114">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="53f1a-114">\<behaviors></span></span>](behaviors-of-workflow.md)|<span data-ttu-id="53f1a-115">本节定义**serviceBehaviors**集合。</span><span class="sxs-lookup"><span data-stu-id="53f1a-115">This section defines the **serviceBehaviors** collection.</span></span>  <span data-ttu-id="53f1a-116">集合中的每个元素定义服务所使用的行为元素。</span><span class="sxs-lookup"><span data-stu-id="53f1a-116">Each element in the collection defines behavior elements consumed by services.</span></span> <span data-ttu-id="53f1a-117">每个行为元素都由其唯一**名称**属性标识。</span><span class="sxs-lookup"><span data-stu-id="53f1a-117">Each behavior element is identified by its unique **name** attribute.</span></span>|  
|[<span data-ttu-id="53f1a-118">\<tracking></span><span class="sxs-lookup"><span data-stu-id="53f1a-118">\<tracking></span></span>](tracking.md)|<span data-ttu-id="53f1a-119">表示一个配置节，用于定义工作流服务的跟踪设置。</span><span class="sxs-lookup"><span data-stu-id="53f1a-119">Represents a configuration section for defining tracking settings for a workflow service.</span></span><br /><br /> <span data-ttu-id="53f1a-120">有关工作流跟踪及其配置的详细信息，请参阅工作流[跟踪和跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)和[配置工作流跟踪](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="53f1a-120">For more information in workflow tracking and its configuration, see [Workflow Tracking and Tracing](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md) and [Configuring Tracking for a Workflow](../../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="53f1a-121">父元素</span><span class="sxs-lookup"><span data-stu-id="53f1a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="53f1a-122">元素</span><span class="sxs-lookup"><span data-stu-id="53f1a-122">Element</span></span>|<span data-ttu-id="53f1a-123">描述</span><span class="sxs-lookup"><span data-stu-id="53f1a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="53f1a-124">\<configuration></span><span class="sxs-lookup"><span data-stu-id="53f1a-124">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="53f1a-125">.NET 配置文件中的所有配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="53f1a-125">The root element for all configuration elements in a .NET configuration file.</span></span>|
