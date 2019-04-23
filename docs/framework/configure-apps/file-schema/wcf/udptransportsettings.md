---
title: <udpTransportSettings>
ms.date: 03/30/2017
ms.assetid: 842d92e9-6199-4ec5-b2d1-58533054e1f0
ms.openlocfilehash: f5be9681dc69fd68dfdfa90f4eb305dc4aa4514b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59218493"
---
# <a name="udptransportsettings"></a><span data-ttu-id="5fb52-101">\<udpTransportSettings></span><span class="sxs-lookup"><span data-stu-id="5fb52-101">\<udpTransportSettings></span></span>
<span data-ttu-id="5fb52-102">此配置元素公开的 UDP 传输设置[ \<udpDiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="5fb52-102">This configuration element exposes UDP transport settings for [\<udpDiscoveryEndpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md).</span></span>  
  
<span data-ttu-id="5fb52-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5fb52-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="5fb52-104">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="5fb52-104">\<standardEndpoints></span></span>  
<span data-ttu-id="5fb52-105">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="5fb52-105">\<udpDiscoveryEndpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fb52-106">语法</span><span class="sxs-lookup"><span data-stu-id="5fb52-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <udpDiscoveryEndpoint>
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
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fb52-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5fb52-107">Attributes and Elements</span></span>  
 <span data-ttu-id="5fb52-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5fb52-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fb52-109">特性</span><span class="sxs-lookup"><span data-stu-id="5fb52-109">Attributes</span></span>  
  
|<span data-ttu-id="5fb52-110">特性</span><span class="sxs-lookup"><span data-stu-id="5fb52-110">Attribute</span></span>|<span data-ttu-id="5fb52-111">描述</span><span class="sxs-lookup"><span data-stu-id="5fb52-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5fb52-112">duplicateMessageHistoryLength</span><span class="sxs-lookup"><span data-stu-id="5fb52-112">duplicateMessageHistoryLength</span></span>|<span data-ttu-id="5fb52-113">一个整数，指定传输用于标识重复消息的最大消息哈希数。</span><span class="sxs-lookup"><span data-stu-id="5fb52-113">An integer that specifies the maximum number of message hashes used by the transport for identifying duplicate messages.</span></span>  <span data-ttu-id="5fb52-114">将在 TransportManager 级别进行重复检测。</span><span class="sxs-lookup"><span data-stu-id="5fb52-114">Duplicate detection will be done at the TransportManager level.</span></span> <span data-ttu-id="5fb52-115">将此属性设置为 0 即可禁用重复检测。</span><span class="sxs-lookup"><span data-stu-id="5fb52-115">Setting this property to 0 disables duplicate detection.</span></span><br /><br /> <span data-ttu-id="5fb52-116">系统管理员或开发人员可以使用此特性关闭重复消息检测算法。</span><span class="sxs-lookup"><span data-stu-id="5fb52-116">This attribute allows system administrators or developers to turn off duplicate message detection algorithms.</span></span> <span data-ttu-id="5fb52-117">如果您希望实现自己的重复检测算法，可能需要这一功能。</span><span class="sxs-lookup"><span data-stu-id="5fb52-117">This may be desirable if you want to implement your own duplicate detection algorithm.</span></span><br /><br /> <span data-ttu-id="5fb52-118">默认值为 4112。</span><span class="sxs-lookup"><span data-stu-id="5fb52-118">The default is 4112.</span></span>|  
|<span data-ttu-id="5fb52-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5fb52-119">maxBufferPoolSize</span></span>|<span data-ttu-id="5fb52-120">一个整数，指定传输使用的任何缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5fb52-120">An integer that specifies the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="5fb52-121">maxMulticastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="5fb52-121">maxMulticastRetransmitCount</span></span>|<span data-ttu-id="5fb52-122">一个整数，指定应重新传输消息的最大次数（包括第一次发送）。</span><span class="sxs-lookup"><span data-stu-id="5fb52-122">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span><br /><br /> <span data-ttu-id="5fb52-123">默认值为 2。</span><span class="sxs-lookup"><span data-stu-id="5fb52-123">The default is 2.</span></span>|  
|<span data-ttu-id="5fb52-124">maxPendingMessageCount</span><span class="sxs-lookup"><span data-stu-id="5fb52-124">maxPendingMessageCount</span></span>|<span data-ttu-id="5fb52-125">一个整数，指定已经接收但尚未从单个通道实例的 InputQueue 中移除的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="5fb52-125">An integer that specifies the maximum number of messages that have been received but not yet removed from the InputQueue for an individual channel instance.</span></span>  <span data-ttu-id="5fb52-126">如果 InputQueue 已达到挂起消息计数上限，则将丢弃消息。</span><span class="sxs-lookup"><span data-stu-id="5fb52-126">If the InputQueue has hit its pending message count limit, the message will be dropped.</span></span><br /><br /> <span data-ttu-id="5fb52-127">默认值为 32。</span><span class="sxs-lookup"><span data-stu-id="5fb52-127">The default is 32.</span></span>|  
|<span data-ttu-id="5fb52-128">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5fb52-128">maxReceivedMessageSize</span></span>|<span data-ttu-id="5fb52-129">一个整数，指定绑定可处理的消息的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5fb52-129">An integer that specifies the maximum size for a message that can be processed by the binding.</span></span><br /><br /> <span data-ttu-id="5fb52-130">默认值为 65507。</span><span class="sxs-lookup"><span data-stu-id="5fb52-130">The default value is 65507.</span></span>|  
|<span data-ttu-id="5fb52-131">maxUnicastRetransmitCount</span><span class="sxs-lookup"><span data-stu-id="5fb52-131">maxUnicastRetransmitCount</span></span>|<span data-ttu-id="5fb52-132">一个整数，指定应重新传输消息的最大次数（包括第一次发送）。</span><span class="sxs-lookup"><span data-stu-id="5fb52-132">An integer that specifies the maximum number of times the message should be retransmitted (in addition to the first send).</span></span>  <span data-ttu-id="5fb52-133">如果将消息发送到单播地址，并且收到的响应消息中带有相应的 RelatesTo 标头，重新传输可能会提前终止（在达到配置的重新传输次数之前）。</span><span class="sxs-lookup"><span data-stu-id="5fb52-133">If the message is sent to a unicast address and a response message is received with a corresponding RelatesTo header, then retransmission may terminate early (before retransmitting the configured number of times).</span></span><br /><br /> <span data-ttu-id="5fb52-134">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="5fb52-134">The default value is 1.</span></span>|  
|<span data-ttu-id="5fb52-135">multicastInterfaceId</span><span class="sxs-lookup"><span data-stu-id="5fb52-135">multicastInterfaceId</span></span>|<span data-ttu-id="5fb52-136">一个字符串，唯一标识在多宿主计算机上发送和接收多播流量时应使用的网络适配器。</span><span class="sxs-lookup"><span data-stu-id="5fb52-136">A string that uniquely identifies the network adapter that should be used when sending and receiving multicast traffic on multi-homed machines.</span></span> <span data-ttu-id="5fb52-137">在运行时，传输将使用此特性值来查找接口索引，然后使用该索引设置 `IP_MULTICAST_IF` 和 `IPV6_MULTICAST_IF` 套接字选项。</span><span class="sxs-lookup"><span data-stu-id="5fb52-137">At runtime, the transport will use this attribute value to lookup the interface index, which is then used to set the `IP_MULTICAST_IF` and `IPV6_MULTICAST_IF` socket options.</span></span>  <span data-ttu-id="5fb52-138">加入多播组时将使用相同的接口索引（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="5fb52-138">The same interface index will be used when joining a multicast group, if applicable.</span></span><br /><br /> <span data-ttu-id="5fb52-139">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="5fb52-139">The default value is `null`.</span></span>|  
|<span data-ttu-id="5fb52-140">socketReceiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="5fb52-140">socketReceiveBufferSize</span></span>|<span data-ttu-id="5fb52-141">一个整数，指定基础 WinSock 套接字上接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="5fb52-141">An integer that specifies the receive buffer size on the underlying WinSock socket.</span></span><br /><br /> <span data-ttu-id="5fb52-142">接收通道的用户可以对绑定使用此特性，以控制系统在接收数据时的行为。</span><span class="sxs-lookup"><span data-stu-id="5fb52-142">A user of a receiving channel can use this attribute on the Binding to control how the system behaves when it receives data.</span></span>  <span data-ttu-id="5fb52-143">例如，假定应用程序使用入站 WCF 消息时达到了最大阈值，对此特性使用较高的值将允许消息在等待应用程序处理时在 WinSock 缓冲区中堆叠。</span><span class="sxs-lookup"><span data-stu-id="5fb52-143">For example, given an application that is consuming inbound WCF messages at the maximum threshold, using a higher value for this attribute would allow messages to stack up in the WinSock buffer while waiting for the application to be able to process them.</span></span>  <span data-ttu-id="5fb52-144">在同样的情况下，使用较低的值将导致消息被丢弃。</span><span class="sxs-lookup"><span data-stu-id="5fb52-144">Using a lower value in the same situation would result in messages getting dropped.</span></span> <span data-ttu-id="5fb52-145">此特性公开基础 WinSock`SO_RCVBUF`套接字选项。此属性的值必须是至少的大小`maxReceivedMessageSize`。</span><span class="sxs-lookup"><span data-stu-id="5fb52-145">This attribute exposes the underlying WinSock `SO_RCVBUF` socket option.This attribute value must be at least the size of `maxReceivedMessageSize`.</span></span>   <span data-ttu-id="5fb52-146">将其设置为一个值小于`maxReceivedMessageSize`将导致运行时异常。</span><span class="sxs-lookup"><span data-stu-id="5fb52-146">Setting it to a value smaller than the `maxReceivedMessageSize` will result in a runtime exception.</span></span><br /><br /> <span data-ttu-id="5fb52-147">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="5fb52-147">The default value is 65536.</span></span>|  
|<span data-ttu-id="5fb52-148">timeToLive</span><span class="sxs-lookup"><span data-stu-id="5fb52-148">timeToLive</span></span>|<span data-ttu-id="5fb52-149">一个整数，指定多播数据包可以遍历的网络段跃点数。</span><span class="sxs-lookup"><span data-stu-id="5fb52-149">An integer that specifies the number of network segment hops that a multicast packet can traverse.</span></span>  <span data-ttu-id="5fb52-150">此特性公开与 `IP_MULTICAST_TTL` 和 `IP_TTL` 套接字选项关联的功能。</span><span class="sxs-lookup"><span data-stu-id="5fb52-150">This attribute exposes the functionality associated with the `IP_MULTICAST_TTL` and `IP_TTL` socket options.</span></span><br /><br /> <span data-ttu-id="5fb52-151">默认值为 1。</span><span class="sxs-lookup"><span data-stu-id="5fb52-151">The default value is 1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fb52-152">子元素</span><span class="sxs-lookup"><span data-stu-id="5fb52-152">Child Elements</span></span>  
 <span data-ttu-id="5fb52-153">无。</span><span class="sxs-lookup"><span data-stu-id="5fb52-153">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fb52-154">父元素</span><span class="sxs-lookup"><span data-stu-id="5fb52-154">Parent Elements</span></span>  
  
|<span data-ttu-id="5fb52-155">元素</span><span class="sxs-lookup"><span data-stu-id="5fb52-155">Element</span></span>|<span data-ttu-id="5fb52-156">描述</span><span class="sxs-lookup"><span data-stu-id="5fb52-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5fb52-157">\<udpDiscoveryEndpoint></span><span class="sxs-lookup"><span data-stu-id="5fb52-157">\<udpDiscoveryEndpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|<span data-ttu-id="5fb52-158">具有固定发现协定和 UDP 传输绑定的标准终结点。</span><span class="sxs-lookup"><span data-stu-id="5fb52-158">A standard endpoint that has fixed discovery contract and UDP transport binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5fb52-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="5fb52-159">See also</span></span>

- <xref:System.ServiceModel.Discovery.UdpTransportSettings>
