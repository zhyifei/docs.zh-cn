---
title: <channelSettings>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 94a4457f-f43f-458d-a47e-2d11103ee75e
ms.openlocfilehash: f70e30c903fa9bfc3f5d6054ef2ec34bf1b3cba1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790203"
---
# <a name="channelsettings"></a><span data-ttu-id="99547-101">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="99547-101">\<channelSettings></span></span>
<span data-ttu-id="99547-102">指定通道缓存的设置。</span><span class="sxs-lookup"><span data-stu-id="99547-102">Specifies the settings of the channel cache.</span></span>  
  
<span data-ttu-id="99547-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="99547-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="99547-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="99547-104">\<behaviors></span></span>  
<span data-ttu-id="99547-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="99547-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="99547-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="99547-106">\<behavior></span></span>  
<span data-ttu-id="99547-107">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="99547-107">\<sendMessageChannelCache></span></span>  
<span data-ttu-id="99547-108">\<channelSettings></span><span class="sxs-lookup"><span data-stu-id="99547-108">\<channelSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99547-109">语法</span><span class="sxs-lookup"><span data-stu-id="99547-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <sendMessageChannelCache allowUnsafeCaching="Boolean">
        <channelSettings idleTimeout="TimeSpan" 
                         leaseTimeout="TimeSpan" 
                         maxItemsInCache="Integer" />
      </sendMessageChannelCache>
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99547-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="99547-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99547-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="99547-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99547-112">特性</span><span class="sxs-lookup"><span data-stu-id="99547-112">Attributes</span></span>  
  
|<span data-ttu-id="99547-113">特性</span><span class="sxs-lookup"><span data-stu-id="99547-113">Attribute</span></span>|<span data-ttu-id="99547-114">描述</span><span class="sxs-lookup"><span data-stu-id="99547-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99547-115">idleTimeout</span><span class="sxs-lookup"><span data-stu-id="99547-115">idleTimeout</span></span>|<span data-ttu-id="99547-116">一个 TimeSpan 值，指定对象在被释放之前可在缓存中保持空闲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="99547-116">A TimeSpan value that specifies the maximum interval of time for which the object can remain idle in the cache before being disposed.</span></span>|  
|<span data-ttu-id="99547-117">leaseTimeout</span><span class="sxs-lookup"><span data-stu-id="99547-117">leaseTimeout</span></span>|<span data-ttu-id="99547-118">一个 TimeSpan 值，指定的时间间隔后从缓存移除对象。</span><span class="sxs-lookup"><span data-stu-id="99547-118">A TimeSpan value that specifies  the interval of time after which an object is removed from the cache.</span></span>|  
|<span data-ttu-id="99547-119">maxItemsInCache</span><span class="sxs-lookup"><span data-stu-id="99547-119">maxItemsInCache</span></span>|<span data-ttu-id="99547-120">一个整数，指定可以位于缓存中的最大对象数。</span><span class="sxs-lookup"><span data-stu-id="99547-120">An integer that specifies the maximum number of objects that can be in the cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99547-121">子元素</span><span class="sxs-lookup"><span data-stu-id="99547-121">Child Elements</span></span>  
 <span data-ttu-id="99547-122">无。</span><span class="sxs-lookup"><span data-stu-id="99547-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99547-123">父元素</span><span class="sxs-lookup"><span data-stu-id="99547-123">Parent Elements</span></span>  
  
|<span data-ttu-id="99547-124">元素</span><span class="sxs-lookup"><span data-stu-id="99547-124">Element</span></span>|<span data-ttu-id="99547-125">描述</span><span class="sxs-lookup"><span data-stu-id="99547-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99547-126">\<sendMessageChannelCache></span><span class="sxs-lookup"><span data-stu-id="99547-126">\<sendMessageChannelCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md)|<span data-ttu-id="99547-127">一种服务行为，允许自定义的缓存共享级别、 通道工厂缓存的设置和用于将消息发送到服务终结点使用 Send 消息传递活动的工作流的通道缓存设置。</span><span class="sxs-lookup"><span data-stu-id="99547-127">A service behavior that enables the customization of the cache sharing levels, the settings of the channel factory cache, and the settings of the channel cache for workflows that send messages to service endpoints using Send messaging activities.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99547-128">备注</span><span class="sxs-lookup"><span data-stu-id="99547-128">Remarks</span></span>  
 <span data-ttu-id="99547-129">此服务行为适用于将消息发送给服务终结点的工作流。</span><span class="sxs-lookup"><span data-stu-id="99547-129">This service behavior is intended for workflows that send messages to service endpoints.</span></span> <span data-ttu-id="99547-130">这些工作流通常是客户端工作流，但也可以是在 <xref:System.ServiceModel.WorkflowServiceHost> 中承载的工作流服务。</span><span class="sxs-lookup"><span data-stu-id="99547-130">These workflows are typically client workflows but could also be workflow services that are hosted in a <xref:System.ServiceModel.WorkflowServiceHost>.</span></span>  
  
 <span data-ttu-id="99547-131">默认情况下，在 <xref:System.ServiceModel.WorkflowServiceHost> 承载的工作流中，由 <xref:System.ServiceModel.Activities.Send> 消息传递活动使用的缓存可在 <xref:System.ServiceModel.WorkflowServiceHost> 中的所有工作流实例中共享（主机级缓存）。</span><span class="sxs-lookup"><span data-stu-id="99547-131">By default, in a workflow hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache used by <xref:System.ServiceModel.Activities.Send> messaging activities is shared across all workflow instances in the <xref:System.ServiceModel.WorkflowServiceHost> (host-level caching).</span></span> <span data-ttu-id="99547-132">对于未由 <xref:System.ServiceModel.WorkflowServiceHost> 承载的客户端工作流，缓存仅对该工作流实例可用（实例级缓存）。</span><span class="sxs-lookup"><span data-stu-id="99547-132">For a client workflow that is not hosted by a <xref:System.ServiceModel.WorkflowServiceHost>, the cache is available only to the workflow instance (instance-level caching).</span></span> <span data-ttu-id="99547-133">对于已在配置中定义了终结点的工作流中的所有 Send 活动，默认情况下为禁用缓存。</span><span class="sxs-lookup"><span data-stu-id="99547-133">Caching is disabled by default for any send activity in your workflow that has endpoints defined in configuration.</span></span>  
  
 <span data-ttu-id="99547-134">有关如何更改默认的缓存共享级别以及通道工厂和通道缓存的缓存设置的详细信息，请参阅[更改发送活动的缓存共享级别](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)。</span><span class="sxs-lookup"><span data-stu-id="99547-134">For more information about how to change the default cache sharing levels and cache settings for the channel factory and channel cache, see [Changing the Cache Sharing Levels for Send Activities](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="99547-135">示例</span><span class="sxs-lookup"><span data-stu-id="99547-135">Example</span></span>  
 <span data-ttu-id="99547-136">在承载的工作流服务中，可以在应用程序配置文件中指定工厂缓存和通道缓存设置。</span><span class="sxs-lookup"><span data-stu-id="99547-136">In a hosted workflow service, you can specify the factory cache and channel cache settings in the application configuration file.</span></span> <span data-ttu-id="99547-137">为此，应添加一个包含工厂和通道缓存的缓存设置的服务行为，并将此服务行为添加到您的服务中。</span><span class="sxs-lookup"><span data-stu-id="99547-137">To do so, add a service behavior that contains the cache settings for the factory and channel cache and add this service behavior to your service.</span></span> <span data-ttu-id="99547-138">下面的示例显示了包含的配置文件的内容**MyChannelCacheBehavior**服务使用自定义工厂缓存和通道缓存设置的行为。</span><span class="sxs-lookup"><span data-stu-id="99547-138">The following example shows the contents of a configuration file that contains the **MyChannelCacheBehavior**  service behavior with the custom factory cache and channel cache settings.</span></span> <span data-ttu-id="99547-139">此服务行为添加到服务**behaviorConfiguarion**属性。</span><span class="sxs-lookup"><span data-stu-id="99547-139">This service behavior is added to the service through the **behaviorConfiguarion** attribute.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="99547-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="99547-140">See also</span></span>

- <xref:System.ServiceModel.Activities.SendMessageChannelCache>
- <xref:System.ServiceModel.Activities.Configuration.SendMessageChannelCacheElement>
- <xref:System.ServiceModel.Activities.Send>
- <xref:System.ServiceModel.Activities.ChannelCacheSettings>
- [<span data-ttu-id="99547-141">更改发送活动的缓存共享级别</span><span class="sxs-lookup"><span data-stu-id="99547-141">Changing the Cache Sharing Levels for Send Activities</span></span>](../../../../../docs/framework/wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md)
