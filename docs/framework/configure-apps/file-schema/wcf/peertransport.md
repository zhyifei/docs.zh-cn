---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: d896953a7ed31fdaf5f357a8721c7d085d50bc56
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400059"
---
# <a name="peertransport"></a><span data-ttu-id="c6433-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="c6433-101">\<peerTransport></span></span>
<span data-ttu-id="c6433-102">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="c6433-102">Defines a peer transport for a custom binding.</span></span>  
  
<span data-ttu-id="c6433-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6433-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6433-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c6433-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c6433-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c6433-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c6433-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c6433-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c6433-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="c6433-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c6433-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<peerTransport >**</span><span class="sxs-lookup"><span data-stu-id="c6433-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6433-109">语法</span><span class="sxs-lookup"><span data-stu-id="c6433-109">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6433-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c6433-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c6433-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c6433-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6433-112">特性</span><span class="sxs-lookup"><span data-stu-id="c6433-112">Attributes</span></span>  
  
|<span data-ttu-id="c6433-113">特性</span><span class="sxs-lookup"><span data-stu-id="c6433-113">Attribute</span></span>|<span data-ttu-id="c6433-114">描述</span><span class="sxs-lookup"><span data-stu-id="c6433-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6433-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="c6433-115">listenIpAddress</span></span>|<span data-ttu-id="c6433-116">一个字符串，指定对等节点将在其上侦听 TCP 消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c6433-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="c6433-117">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c6433-117">The default is `null`.</span></span>|  
|<span data-ttu-id="c6433-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="c6433-118">maxBufferPoolSize</span></span>|<span data-ttu-id="c6433-119">一个正整数，指定缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c6433-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="c6433-120">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="c6433-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="c6433-121">WCF 的许多组件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c6433-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="c6433-122">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="c6433-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="c6433-123">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="c6433-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="c6433-124">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="c6433-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="c6433-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="c6433-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="c6433-126">一个正整数，定义包括标头在内的最大消息大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c6433-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="c6433-127">如果消息对于接收方而言太大，则消息发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="c6433-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="c6433-128">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="c6433-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c6433-129">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="c6433-129">The default is 65536.</span></span>|  
|<span data-ttu-id="c6433-130">端口</span><span class="sxs-lookup"><span data-stu-id="c6433-130">port</span></span>|<span data-ttu-id="c6433-131">一个整数，指定此绑定将用于处理对等通道 TCP 消息的网络接口端口。</span><span class="sxs-lookup"><span data-stu-id="c6433-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="c6433-132">该值必须介于 <xref:System.Net.IPEndPoint.MinPort> 和 <xref:System.Net.IPEndPoint.MaxPort> 之间。</span><span class="sxs-lookup"><span data-stu-id="c6433-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="c6433-133">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="c6433-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6433-134">子元素</span><span class="sxs-lookup"><span data-stu-id="c6433-134">Child Elements</span></span>  
  
|<span data-ttu-id="c6433-135">元素</span><span class="sxs-lookup"><span data-stu-id="c6433-135">Element</span></span>|<span data-ttu-id="c6433-136">描述</span><span class="sxs-lookup"><span data-stu-id="c6433-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6433-137">\<security></span><span class="sxs-lookup"><span data-stu-id="c6433-137">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="c6433-138">定义此传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c6433-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="c6433-139">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="c6433-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c6433-140">父元素</span><span class="sxs-lookup"><span data-stu-id="c6433-140">Parent Elements</span></span>  
  
|<span data-ttu-id="c6433-141">元素</span><span class="sxs-lookup"><span data-stu-id="c6433-141">Element</span></span>|<span data-ttu-id="c6433-142">描述</span><span class="sxs-lookup"><span data-stu-id="c6433-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6433-143">\<binding></span><span class="sxs-lookup"><span data-stu-id="c6433-143">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c6433-144">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="c6433-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6433-145">备注</span><span class="sxs-lookup"><span data-stu-id="c6433-145">Remarks</span></span>  
 <span data-ttu-id="c6433-146">此传输不可用于包含请求/答复操作的协定。</span><span class="sxs-lookup"><span data-stu-id="c6433-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6433-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6433-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c6433-148">传输</span><span class="sxs-lookup"><span data-stu-id="c6433-148">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="c6433-149">选择传输</span><span class="sxs-lookup"><span data-stu-id="c6433-149">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c6433-150">绑定</span><span class="sxs-lookup"><span data-stu-id="c6433-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c6433-151">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c6433-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c6433-152">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c6433-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c6433-153">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c6433-153">\<customBinding></span></span>](custombinding.md)
