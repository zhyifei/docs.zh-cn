---
title: <behavior>工作流<serviceBehaviors>的
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
ms.openlocfilehash: 071cff8e9f6ec3fa0546a07d19160869d8b43f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152315"
---
# <a name="behavior-of-servicebehaviors-of-workflow"></a><span data-ttu-id="d885d-102">\<\<服务行为>>工作流</span><span class="sxs-lookup"><span data-stu-id="d885d-102">\<behavior> of \<serviceBehaviors> of workflow</span></span>
<span data-ttu-id="d885d-103">**行为**元素包含服务行为的设置集合。</span><span class="sxs-lookup"><span data-stu-id="d885d-103">The **behavior** element contains a collection of settings for the behavior of a service.</span></span> <span data-ttu-id="d885d-104">每个行为都按其**名称**编制索引。</span><span class="sxs-lookup"><span data-stu-id="d885d-104">Each behavior is indexed by its **name**.</span></span> <span data-ttu-id="d885d-105">服务可以使用[\<终结点>](../wcf/endpoint-element.md)元素**的行为配置**属性通过此名称链接到每个行为。</span><span class="sxs-lookup"><span data-stu-id="d885d-105">Services can link to each behavior through this name using the **behaviorConfiguration** attribute of the [\<endpoint>](../wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="d885d-106">这样，终结点可以共享公共行为配置而不用重新定义设置。</span><span class="sxs-lookup"><span data-stu-id="d885d-106">This allows endpoints to share common behavior configurations without redefining the settings.</span></span>  
  
<span data-ttu-id="d885d-107">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d885d-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d885d-108">&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d885d-108">&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)</span></span>\
<span data-ttu-id="d885d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d885d-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors-of-workflow.md)</span></span>\
<span data-ttu-id="d885d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务行为>**](servicebehaviors-of-workflow.md)</span><span class="sxs-lookup"><span data-stu-id="d885d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors-of-workflow.md)</span></span>\
<span data-ttu-id="d885d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<行为>**</span><span class="sxs-lookup"><span data-stu-id="d885d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d885d-112">语法</span><span class="sxs-lookup"><span data-stu-id="d885d-112">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d885d-113">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d885d-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d885d-114">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d885d-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d885d-115">属性</span><span class="sxs-lookup"><span data-stu-id="d885d-115">Attributes</span></span>  
  
|<span data-ttu-id="d885d-116">Attribute</span><span class="sxs-lookup"><span data-stu-id="d885d-116">Attribute</span></span>|<span data-ttu-id="d885d-117">说明</span><span class="sxs-lookup"><span data-stu-id="d885d-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d885d-118">name</span><span class="sxs-lookup"><span data-stu-id="d885d-118">name</span></span>|<span data-ttu-id="d885d-119">一个包含行为的配置名称的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="d885d-119">A unique string that contains the configuration name of the behavior.</span></span> <span data-ttu-id="d885d-120">此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。</span><span class="sxs-lookup"><span data-stu-id="d885d-120">This value is a user-defined string that must be unique, since it acts as the identification string for the element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d885d-121">子元素</span><span class="sxs-lookup"><span data-stu-id="d885d-121">Child Elements</span></span>  
  
|<span data-ttu-id="d885d-122">元素</span><span class="sxs-lookup"><span data-stu-id="d885d-122">Element</span></span>|<span data-ttu-id="d885d-123">说明</span><span class="sxs-lookup"><span data-stu-id="d885d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d885d-124">\<缓冲区接收></span><span class="sxs-lookup"><span data-stu-id="d885d-124">\<bufferReceive></span></span>](bufferreceive.md)|<span data-ttu-id="d885d-125">一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。</span><span class="sxs-lookup"><span data-stu-id="d885d-125">A service behavior that enables a service to use buffered receive processing, which enables a workflow service to process out-of-order messages.</span></span>|  
|[<span data-ttu-id="d885d-126">\<路由></span><span class="sxs-lookup"><span data-stu-id="d885d-126">\<routing></span></span>](../wcf/routing-of-servicebehavior.md)|<span data-ttu-id="d885d-127">一种服务行为，允许服务使用 <xref:System.Activities.Tracking.EtwTrackingParticipant> 来利用 ETW 跟踪。</span><span class="sxs-lookup"><span data-stu-id="d885d-127">A service behavior that allows a service to utilize ETW tracking using an <xref:System.Activities.Tracking.EtwTrackingParticipant>.</span></span>|  
|[<span data-ttu-id="d885d-128">\<发送消息通道缓存></span><span class="sxs-lookup"><span data-stu-id="d885d-128">\<sendMessageChannelCache></span></span>](sendmessagechannelcache.md)|<span data-ttu-id="d885d-129">一种服务行为，该行为支持缓存共享级别的自定义、通道工厂缓存的设置，以及使用 Send 消息传递活动将消息发送给服务终结点的工作流通道缓存的设置。</span><span class="sxs-lookup"><span data-stu-id="d885d-129">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
|[<span data-ttu-id="d885d-130">\<sqlWorkflow 实例存储></span><span class="sxs-lookup"><span data-stu-id="d885d-130">\<sqlWorkflowInstanceStore></span></span>](sqlworkflowinstancestore.md)|<span data-ttu-id="d885d-131">一种服务行为，它允许您配置 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 功能，该功能支持将工作流服务实例的状态信息保持到 SQL Server 2005 或 SQL Server 2008 数据库中。</span><span class="sxs-lookup"><span data-stu-id="d885d-131">A service behavior that allows you to configure the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> feature, which supports persisting state information for workflow service instances into an SQL Server 2005 or SQL Server 2008 database.</span></span>|  
|[<span data-ttu-id="d885d-132">\<工作流 空闲></span><span class="sxs-lookup"><span data-stu-id="d885d-132">\<workflowIdle></span></span>](workflowidle.md)|<span data-ttu-id="d885d-133">一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。</span><span class="sxs-lookup"><span data-stu-id="d885d-133">A service behavior that controls when idle workflow instances are unloaded and persisted.</span></span>|  
|[<span data-ttu-id="d885d-134">\<工作流实例管理></span><span class="sxs-lookup"><span data-stu-id="d885d-134">\<workflowInstanceManagement></span></span>](workflowinstancemanagement.md)|<span data-ttu-id="d885d-135">一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。</span><span class="sxs-lookup"><span data-stu-id="d885d-135">A service behavior that enables you to specify settings that control how workflow instances are run, including persistence, unhandled Exception behavior and idle behavior.</span></span>|  
|[<span data-ttu-id="d885d-136">\<工作流未处理异常></span><span class="sxs-lookup"><span data-stu-id="d885d-136">\<workflowUnhandledException></span></span>](workflowunhandledexception.md)|<span data-ttu-id="d885d-137">一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="d885d-137">A service behavior that enables you to specify the action to take when an unhandled exception occurs within a workflow service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d885d-138">父元素</span><span class="sxs-lookup"><span data-stu-id="d885d-138">Parent Elements</span></span>  
  
|<span data-ttu-id="d885d-139">元素</span><span class="sxs-lookup"><span data-stu-id="d885d-139">Element</span></span>|<span data-ttu-id="d885d-140">说明</span><span class="sxs-lookup"><span data-stu-id="d885d-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d885d-141">\<服务行为></span><span class="sxs-lookup"><span data-stu-id="d885d-141">\<serviceBehaviors></span></span>](servicebehaviors-of-workflow.md)|<span data-ttu-id="d885d-142">服务行为元素的集合。</span><span class="sxs-lookup"><span data-stu-id="d885d-142">A collection of service behavior elements.</span></span>|
