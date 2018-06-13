---
title: '&lt;udpAnnouncementEndpoint&gt; 的 &lt;udpTransportSettings&gt;'
ms.date: 03/30/2017
ms.assetid: a7ddff1a-5eed-4bbc-8580-b95ef8890e1f
ms.openlocfilehash: 624dbada56a609452310218d26c5c6ff0ca49d64
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767071"
---
# <a name="ltudptransportsettingsgt-of-ltudpannouncementendpointgt"></a><span data-ttu-id="cc9ac-102">&lt;udpAnnouncementEndpoint&gt; 的 &lt;udpTransportSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="cc9ac-102">&lt;udpTransportSettings&gt; of &lt;udpAnnouncementEndpoint&gt;</span></span>
<span data-ttu-id="cc9ac-103">此配置元素公开 UDP 传输设置[ \<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-103">This configuration element exposes UDP transport settings for [\<udpAnnoucementEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md).</span></span>  
  
<span data-ttu-id="cc9ac-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cc9ac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="cc9ac-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="cc9ac-105">\<standardEndpoints></span></span>  
<span data-ttu-id="cc9ac-106">\<udpAnnouncementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="cc9ac-106">\<udpAnnouncementEndpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc9ac-107">语法</span><span class="sxs-lookup"><span data-stu-id="cc9ac-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <udpAnnouncementEndpoint>
      <standardEndpoint>
        <updTransportSettings duplicateMessageHistoryLength="Integer" 
                              maxBufferPoolSize="Integer" 
                              maxMulticastRetransmitCount="Integer" 
                              maxPendingMessageCount="Integer" 
                              maxReceivedMessageSize="Integer" 
                              maxUnicastRetransmitCount="Integer" 
                              multicastInterfaceId="String" 
                              socketReceiveBufferSize="Integer" 
                              timeToLive="Integer" />
      </standardEndpoint>
    </udpAnnouncementEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc9ac-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cc9ac-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cc9ac-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc9ac-110">特性</span><span class="sxs-lookup"><span data-stu-id="cc9ac-110">Attributes</span></span>  
  
|<span data-ttu-id="cc9ac-111">特性</span><span class="sxs-lookup"><span data-stu-id="cc9ac-111">Attribute</span></span>|<span data-ttu-id="cc9ac-112">描述</span><span class="sxs-lookup"><span data-stu-id="cc9ac-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cc9ac-113">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="cc9ac-113">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="cc9ac-114">一个整数，指定传输用于标识重复消息的最大消息哈希数。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-114">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="cc9ac-115">将在 TransportManager 级别进行重复检测。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-115">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="cc9ac-116">将此属性设置为 0 即可禁用重复检测。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-116">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="cc9ac-117">系统管理员或开发人员可以使用此特性关闭重复消息检测算法。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-117">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="cc9ac-118">如果您希望实现自己的重复检测算法，可能需要这一功能。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-118">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="cc9ac-119">默认值为 4112。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-119">The default is 4112.</span></span>|  
|<span data-ttu-id="cc9ac-120">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="cc9ac-120">maxBufferPoolSize</span></span>|<span data-ttu-id="cc9ac-121">一个整数，指定传输使用的任何缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-121">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="cc9ac-122">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="cc9ac-122">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="cc9ac-123">一个整数，指定应重新传输消息的最大次数（包括第一次发送）。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-123">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="cc9ac-124">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-124">The default is 2.</span></span>|  
|<span data-ttu-id="cc9ac-125">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="cc9ac-125">maxPendingMessageCount</span></span>|<span data-ttu-id="cc9ac-126">一个整数，指定已经接收但尚未从单个通道实例的 InputQueue 中移除的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-126">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="cc9ac-127">如果 InputQueue 已达到挂起消息计数上限，则将丢弃消息。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-127">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="cc9ac-128">默认值为 32。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-128">The default is 32.</span></span>|  
|<span data-ttu-id="cc9ac-129">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="cc9ac-129">maxReceivedMessageSize</span></span>|<span data-ttu-id="cc9ac-130">一个整数，指定绑定可处理的消息的最大大小。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-130">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="cc9ac-131">默认值为 65507。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-131">The default value is 65507.</span></span>|  
|<span data-ttu-id="cc9ac-132">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="cc9ac-132">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="cc9ac-133">一个整数，指定应重新传输消息的最大次数（包括第一次发送）。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-133">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="cc9ac-134">如果将消息发送到单播地址，并且收到的响应消息中带有相应的 RelatesTo 标头，重新传输可能会提前终止（在达到配置的重新传输次数之前）。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-134">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="cc9ac-135">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-135">The default value is 1.</span></span>|  
|<span data-ttu-id="cc9ac-136">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="cc9ac-136">multicastInterfaceId</span></span>|<span data-ttu-id="cc9ac-137">一个字符串，唯一标识在多宿主计算机上发送和接收多播流量时应使用的网络适配器。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-137">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="cc9ac-138">在运行时，传输将使用此特性值来查找接口索引，然后使用该索引设置 `IP_MULTICAST_IF` 和 `IPV6_MULTICAST_IF` 套接字选项。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-138">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="cc9ac-139">加入多播组时将使用相同的接口索引（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-139">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="cc9ac-140">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-140">The default value is `null`.</span></span>|  
|<span data-ttu-id="cc9ac-141">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="cc9ac-141">socketReceiveBufferSize</span></span>|<span data-ttu-id="cc9ac-142">一个整数，指定基础 WinSock 套接字上接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-142">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="cc9ac-143">接收通道的用户可以对绑定使用此特性，以控制系统在接收数据时的行为。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-143">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="cc9ac-144">例如，假定应用程序使用入站 WCF 消息时达到了最大阈值，对此特性使用较高的值将允许消息在等待应用程序处理时在 WinSock 缓冲区中堆叠。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-144">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="cc9ac-145">在相同情况下使用较低的值将导致丢弃这些消息。此特性公开基础 WinSock `SO_RCVBUF` 套接字选项。此特性值必须至少为 `maxReceivedMessageSize` 的大小。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-145">Using a lower value in the same situation would result in messages getting dropped.This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="cc9ac-146">如果将此特性值设置为小于 `maxReceivedMessageSize` 的值，会导致运行时异常。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-146">Setting it to a value smaller than the `maxReceivedMessageSize` will result in runtime exception.</span></span><br /><br /> <span data-ttu-id="cc9ac-147">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-147">The default value is 65536.</span></span>|  
|<span data-ttu-id="cc9ac-148">timeToLive</span><span class="sxs-lookup"><span data-stu-id="cc9ac-148">timeToLive</span></span>|<span data-ttu-id="cc9ac-149">一个整数，指定多播数据包可以遍历的网络段跃点数。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-149">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="cc9ac-150">此特性公开与 `IP_MULTICAST_TTL` 和 `IP_TTL` 套接字选项关联的功能。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-150">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="cc9ac-151">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-151">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cc9ac-152">子元素</span><span class="sxs-lookup"><span data-stu-id="cc9ac-152">Child Elements</span></span>  
 <span data-ttu-id="cc9ac-153">无。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cc9ac-154">父元素</span><span class="sxs-lookup"><span data-stu-id="cc9ac-154">Parent Elements</span></span>  
  
|<span data-ttu-id="cc9ac-155">元素</span><span class="sxs-lookup"><span data-stu-id="cc9ac-155">Element</span></span>|<span data-ttu-id="cc9ac-156">描述</span><span class="sxs-lookup"><span data-stu-id="cc9ac-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc9ac-157">\<udpAnnoucementEndpoint ></span><span class="sxs-lookup"><span data-stu-id="cc9ac-157">\<udpAnnoucementEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|<span data-ttu-id="cc9ac-158">具有固定公告协定和 UDP 传输绑定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="cc9ac-158">A standard endpoint that has fixed announcement contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cc9ac-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc9ac-159">See Also</span></span>  
 <xref:System.ServiceModel.Discovery.UdpTransportSettings>
