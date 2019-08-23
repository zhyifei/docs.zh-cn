---
title: <behavior>工作<serviceBehaviors>流的
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 91883c42aa7bc0aa8fa0c63c3c45184ba69225d0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69946081"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="4e947-102">\<工作流的\<serviceBehaviors > 的行为 ></span><span class="sxs-lookup"><span data-stu-id="4e947-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="4e947-103">**行为**元素包含服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="4e947-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="4e947-104">每个行为都按其**名称**编制索引。</span><span class="sxs-lookup"><span data-stu-id="4e947-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="4e947-105">服务可以使用[ \<端点 >](../wcf/endpoint-element.md)元素的**behaviorConfiguration**属性, 通过此名称链接到每个行为。</span><span class="sxs-lookup"><span data-stu-id="4e947-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="4e947-106">这样，终结点可以共享公共行为配置而不用重新定义设置。</span><span class="sxs-lookup"><span data-stu-id="4e947-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="4e947-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4e947-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="4e947-108">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="4e947-108">\<behaviors></span></span>  
<span data-ttu-id="4e947-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4e947-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="4e947-110">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="4e947-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e947-111">语法</span><span class="sxs-lookup"><span data-stu-id="4e947-111">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
      <behavior name="String">
        <bufferReceive maxPendingMessagesPerChannel="Integer" />
        <etwTracking profileName="String" />
        <sendMessageChannelCache allowUnsafeCaching="Boolean">
          <channelSettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
          <factorySettings idleTimeout="TimeSpan" 
                           leaseTimeout="TimeSpan" 
                           maxItemsInCache="Integer" />
        </sendMessageChannelCache>
        <sqlWorkflowInstanceStore connectionStringName="String" 
                                  hostLockRenewalPeriod="TimeSpan" 
                                  instanceCompletionAction="DeleteNothing/DeleteAll" 
                                  instanceEncodingAction="None/GZip" 
                                  instanceLockedExceptionAction="NoRetry/BasicRetry/AggressiveRetry" 
                                  runnableInstancesDetectionPeriod="TimeSpan" />
        <workflowIdle timeToPersist="TimeSpan" 
                      timeToUnload="TimeSpan" />
        <workflowUnhandledException action="Abandon/AbandonAndSuspend/Cancel/Terminate" />
      </behavior>
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4e947-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4e947-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4e947-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4e947-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4e947-114">特性</span><span class="sxs-lookup"><span data-stu-id="4e947-114">Attributes</span></span>  
  
|<span data-ttu-id="4e947-115">特性</span><span class="sxs-lookup"><span data-stu-id="4e947-115">Attribute</span></span>|<span data-ttu-id="4e947-116">描述</span><span class="sxs-lookup"><span data-stu-id="4e947-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4e947-117">NAME</span><span class="sxs-lookup"><span data-stu-id="4e947-117">name</span></span>|<span data-ttu-id="4e947-118">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="4e947-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="4e947-119">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="4e947-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4e947-120">子元素</span><span class="sxs-lookup"><span data-stu-id="4e947-120">Child Elements</span></span>  
  
|<span data-ttu-id="4e947-121">元素</span><span class="sxs-lookup"><span data-stu-id="4e947-121">Element</span></span>|<span data-ttu-id="4e947-122">描述</span><span class="sxs-lookup"><span data-stu-id="4e947-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e947-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="4e947-123">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="4e947-124">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="4e947-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="4e947-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="4e947-125">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="4e947-126">一种服务行为, 允许服务使用<xref:System.Activities.Tracking.EtwTrackingParticipant>来利用 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="4e947-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="4e947-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="4e947-127">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="4e947-128">一种服务行为, 可用于自定义缓存共享级别、通道工厂缓存的设置, 以及使用发送消息传递活动将消息发送到服务终结点的工作流的通道缓存的设置。</span><span class="sxs-lookup"><span data-stu-id="4e947-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="4e947-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="4e947-129">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="4e947-130">一种服务行为, 允许您配置<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>功能, 该功能支持将工作流服务实例的状态信息保留到 SQL Server 2005 或 SQL Server 2008 数据库中。</span><span class="sxs-lookup"><span data-stu-id="4e947-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="4e947-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="4e947-131">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="4e947-132">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="4e947-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="4e947-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="4e947-133">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="4e947-134">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="4e947-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="4e947-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="4e947-135">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="4e947-136">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="4e947-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4e947-137">父元素</span><span class="sxs-lookup"><span data-stu-id="4e947-137">Parent Elements</span></span>  
  
|<span data-ttu-id="4e947-138">元素</span><span class="sxs-lookup"><span data-stu-id="4e947-138">Element</span></span>|<span data-ttu-id="4e947-139">描述</span><span class="sxs-lookup"><span data-stu-id="4e947-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4e947-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="4e947-140">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="4e947-141">服务行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="4e947-141">A collection of service behavior elements.</span></span>|
