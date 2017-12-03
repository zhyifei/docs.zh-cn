---
title: "工作流的 &lt;serviceBehaviors&gt; 的 &lt;behavior&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6a4b718a-1b40-4957-935a-f6122819ab3c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e3a25e0cf9f5390fcc05cf9db0b6071ea94b9a4c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltbehaviorgt-of-ltservicebehaviorsgt-of-workflow"></a>工作流的 &lt;serviceBehaviors&gt; 的 &lt;behavior&gt;
**行为**元素包含服务行为的设置的集合。 每个行为按其**名称**。 服务可以将链接到通过此名称使用每个行为**behaviorConfiguration**属性[\<终结点 >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)元素。 这样，终结点可以共享公共行为配置而不用重新定义设置。  
  
\<系统。ServiceModel >  
\<行为 >  
\<serviceBehaviors >  
\<行为 >  
  
## <a name="syntax"></a>语法  
  
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
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|name|一个包含行为的配置名称的唯一字符串。 此值是用户定义的一个字符串，该字符串必须是唯一的，因为它将充当元素的标识字符串。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<bufferReceive >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/bufferreceive.md)|一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。|  
|[\<路由 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|允许服务，以利用 ETW 跟踪使用的服务行为<xref:System.Activities.Tracking.EtwTrackingParticipant>。|  
|[\<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|允许自定义缓存共享级别、 通道工厂缓存的设置和将消息发送到服务终结点使用消息传递活动发送的工作流通道缓存的设置的服务行为。|  
|[\<sqlWorkflowInstanceStore >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sqlworkflowinstancestore.md)|允许你配置的服务行为<xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>功能，支持到 SQL Server 2005 或 SQL Server 2008 数据库的工作流服务实例的保存状态信息。|  
|[\<workflowIdle >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowidle.md)|一种服务行为，可以控制何时卸载和持久保存空闲工作流实例。|  
|[\<workflowInstanceManagement >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancemanagement.md)|一种服务行为，可用于指定控制工作流实例如何运行的设置，包括持久性、未经处理的异常行为和空闲行为。|  
|[\<workflowUnhandledException >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowunhandledexception.md)|一种服务行为，可用于指定工作流服务中发生未经处理的异常时所采取的操作。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/servicebehaviors-of-workflow.md)|服务行为元素的集合。|
