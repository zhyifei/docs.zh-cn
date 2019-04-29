---
title: <behavior> <serviceBehaviors>的工作流
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 09bd54f4a7d56dc1215b1acd36ff131ba4cba12c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790307"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="da439-102">\<行为 > 的\<serviceBehaviors > 的工作流</span><span class="sxs-lookup"><span data-stu-id="da439-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="da439-103">**行为**元素包含服务行为的设置的集合。</span><span class="sxs-lookup"><span data-stu-id="da439-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="da439-104">每个行为按其**名称**。</span><span class="sxs-lookup"><span data-stu-id="da439-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="da439-105">服务可以将链接到通过此名称使用每个行为**behaviorConfiguration**的属性[\<终结点 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="da439-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="da439-106">这样，终结点可以共享公共行为配置而不用重新定义设置。</span><span class="sxs-lookup"><span data-stu-id="da439-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="da439-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="da439-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="da439-108">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="da439-108">\<behaviors></span></span>  
<span data-ttu-id="da439-109">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="da439-109">\<serviceBehaviors></span></span>  
<span data-ttu-id="da439-110">\<behavior></span><span class="sxs-lookup"><span data-stu-id="da439-110">\<behavior></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da439-111">语法</span><span class="sxs-lookup"><span data-stu-id="da439-111">Syntax</span></span>  
  
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
                                  honstLockRenewalPeriod="TimeSpan" 
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da439-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da439-112">Attributes and Elements</span></span>  
 <span data-ttu-id="da439-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da439-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da439-114">特性</span><span class="sxs-lookup"><span data-stu-id="da439-114">Attributes</span></span>  
  
|<span data-ttu-id="da439-115">特性</span><span class="sxs-lookup"><span data-stu-id="da439-115">Attribute</span></span>|<span data-ttu-id="da439-116">描述</span><span class="sxs-lookup"><span data-stu-id="da439-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da439-117">name</span><span class="sxs-lookup"><span data-stu-id="da439-117">name</span></span>|<span data-ttu-id="da439-118">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="da439-118">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="da439-119">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="da439-119">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da439-120">子元素</span><span class="sxs-lookup"><span data-stu-id="da439-120">Child Elements</span></span>  
  
|<span data-ttu-id="da439-121">元素</span><span class="sxs-lookup"><span data-stu-id="da439-121">Element</span></span>|<span data-ttu-id="da439-122">描述</span><span class="sxs-lookup"><span data-stu-id="da439-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da439-123">\<bufferReceive></span><span class="sxs-lookup"><span data-stu-id="da439-123">\<bufferReceive></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|<span data-ttu-id="da439-124">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="da439-124">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="da439-125">\<routing></span><span class="sxs-lookup"><span data-stu-id="da439-125">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|<span data-ttu-id="da439-126">一种服务行为，允许服务来利用 ETW 跟踪使用<xref:System.Activities.Tracking.EtwTrackingParticipant>。</span><span class="sxs-lookup"><span data-stu-id="da439-126">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="da439-127">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="da439-127">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="da439-128">一种服务行为，允许自定义的缓存共享级别、 通道工厂缓存的设置和用于将消息发送到服务终结点使用 Send 消息传递活动的工作流的通道缓存设置。</span><span class="sxs-lookup"><span data-stu-id="da439-128">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="da439-129">\<sqlWorkflowInstanceStore></span><span class="sxs-lookup"><span data-stu-id="da439-129">\<sqlWorkflowInstanceStore></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|<span data-ttu-id="da439-130">一种服务行为，可用于配置<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>功能，支持到 SQL Server 2005 或 SQL Server 2008 数据库的工作流服务实例状态信息持久保存。</span><span class="sxs-lookup"><span data-stu-id="da439-130">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="da439-131">\<workflowIdle></span><span class="sxs-lookup"><span data-stu-id="da439-131">\<workflowIdle></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|<span data-ttu-id="da439-132">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="da439-132">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="da439-133">\<workflowInstanceManagement></span><span class="sxs-lookup"><span data-stu-id="da439-133">\<workflowInstanceManagement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|<span data-ttu-id="da439-134">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="da439-134">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="da439-135">\<workflowUnhandledException></span><span class="sxs-lookup"><span data-stu-id="da439-135">\<workflowUnhandledException></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|<span data-ttu-id="da439-136">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="da439-136">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="da439-137">父元素</span><span class="sxs-lookup"><span data-stu-id="da439-137">Parent Elements</span></span>  
  
|<span data-ttu-id="da439-138">元素</span><span class="sxs-lookup"><span data-stu-id="da439-138">Element</span></span>|<span data-ttu-id="da439-139">描述</span><span class="sxs-lookup"><span data-stu-id="da439-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da439-140">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="da439-140">\<serviceBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|<span data-ttu-id="da439-141">服务行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="da439-141">A collection of service behavior elements.</span></span>|
