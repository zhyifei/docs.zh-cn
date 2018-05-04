---
title: '&lt;factorySettings&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 202aad17-1b8b-4c87-ad57-4ca5de18ed35
ms.openlocfilehash: 36f0b82afa8aa8738d2927dc52e1b00e07e72bb1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltfactorysettingsgt"></a>&lt;factorySettings&gt;
指定通道工厂缓存的设置。  
  
\<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<sendMessageChannelCache >  
\<factorySettings >  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean" >
        <factorySettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|idleTimeout|一个 TimeSpan 值，指定对象在被释放之前可在缓存中保持空闲的最大时间间隔。|  
|leaseTimeout|一个 TimeSpan 值，指定此时间后从缓存移除一个对象的时间间隔。|  
|maxItemsInCache|一个整数，指定可以位于缓存中的最大对象数。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<sendMessageChannelCache >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|允许自定义缓存共享级别、 通道工厂缓存的设置和将消息发送到服务终结点使用消息传递活动发送的工作流通道缓存的设置的服务行为。|  
  
## <a name="remarks"></a>备注  
 此服务行为适用于将消息发送给服务终结点的工作流。 这些工作流通常是客户端工作流，但也可以是在 <xref:System.ServiceModel.WorkflowServiceHost> 中承载的工作流服务。  
  
 默认情况下，在 <xref:System.ServiceModel.WorkflowServiceHost> 承载的工作流中，由 <xref:System.ServiceModel.Activities.Send> 消息传递活动使用的缓存可在 <xref:System.ServiceModel.WorkflowServiceHost> 中的所有工作流实例中共享（主机级缓存）。 对于未由 <xref:System.ServiceModel.WorkflowServiceHost> 承载的客户端工作流，缓存仅对该工作流实例可用（实例级缓存）。 对于已在配置中定义了终结点的工作流中的所有 Send 活动，默认情况下为禁用缓存。  
  
 有关如何更改默认的缓存共享级别和通道工厂和通道缓存的缓存设置的详细信息，请参阅[更改发送活动的缓存共享级别](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)。  
  
## <a name="example"></a>示例  
 在承载的工作流服务中，可以在应用程序配置文件中指定工厂缓存和通道缓存设置。 为此，应添加一个包含工厂和通道缓存的缓存设置的服务行为，并将此服务行为添加到您的服务中。 下面的示例演示配置文件中包含的内容**MyChannelCacheBehavior**使用自定义工厂缓存和通道缓存设置服务行为。 此服务行为添加到服务通过**behaviorConfiguarion**属性。  
  
```xml  
<configuration>    
  <system.serviceModel>  
    <!-- List of other config sections here -->   
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyChannelCacheBehavior">  
          <sendMessageChannelCache allowUnsafeCaching ="false" >  
            <!-- Control only the host level settings -->   
            <factorySettings maxItemsInCache = "8" idleTimeout = "00:05:00" leaseTimeout="10:00:00" />  
            <channelSettings maxItemsInCache = "32" idleTimeout = "00:05:00" leaseTimeout="00:06:00" />  
          </sendMessageChannelCache>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="MyService" behaviorConfiguration="MyChannelCacheBehavior" />  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Activities.SendMessageChannelCache>  
 <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>  
 <xref:System.ServiceModel.Activities.Send>  
 <xref:System.ServiceModel.Activities.ChannelCacheSettings>  
 [更改发送活动的缓存共享级别](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
