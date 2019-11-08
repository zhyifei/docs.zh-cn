---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 99fb013e052329ae4b99c4db89565ace8935c456
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736504"
---
# <a name="peertransport"></a><span data-ttu-id="c7144-101">\<peerTransport ></span><span class="sxs-lookup"><span data-stu-id="c7144-101">\<peerTransport></span></span>
<span data-ttu-id="c7144-102">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="c7144-102">Defines a peer transport for a custom binding.</span></span>  
  
<span data-ttu-id="c7144-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c7144-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c7144-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="c7144-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c7144-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c7144-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c7144-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c7144-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c7144-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="c7144-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c7144-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<peerTransport >**</span><span class="sxs-lookup"><span data-stu-id="c7144-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<peerTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7144-109">语法</span><span class="sxs-lookup"><span data-stu-id="c7144-109">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c7144-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c7144-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c7144-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c7144-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c7144-112">特性</span><span class="sxs-lookup"><span data-stu-id="c7144-112">Attributes</span></span>  
  
|<span data-ttu-id="c7144-113">特性</span><span class="sxs-lookup"><span data-stu-id="c7144-113">Attribute</span></span>|<span data-ttu-id="c7144-114">描述</span><span class="sxs-lookup"><span data-stu-id="c7144-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c7144-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="c7144-115">listenIpAddress</span></span>|<span data-ttu-id="c7144-116">一个字符串，指定对等节点将在其上侦听 TCP 消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c7144-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="c7144-117">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="c7144-117">The default is `null`.</span></span>|  
|<span data-ttu-id="c7144-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="c7144-118">maxBufferPoolSize</span></span>|<span data-ttu-id="c7144-119">一个正整数，指定缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="c7144-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="c7144-120">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="c7144-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="c7144-121">WCF 的许多组件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="c7144-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="c7144-122">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="c7144-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="c7144-123">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="c7144-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="c7144-124">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="c7144-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="c7144-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="c7144-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="c7144-126">一个正整数，定义包括标头在内的最大消息大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="c7144-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="c7144-127">如果消息对于接收方而言太大，则消息发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="c7144-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="c7144-128">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="c7144-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="c7144-129">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="c7144-129">The default is 65536.</span></span>|  
|<span data-ttu-id="c7144-130">端口</span><span class="sxs-lookup"><span data-stu-id="c7144-130">port</span></span>|<span data-ttu-id="c7144-131">一个整数，指定此绑定将用于处理对等通道 TCP 消息的网络接口端口。</span><span class="sxs-lookup"><span data-stu-id="c7144-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="c7144-132">该值必须介于 <xref:System.Net.IPEndPoint.MinPort> 和 <xref:System.Net.IPEndPoint.MaxPort> 之间。</span><span class="sxs-lookup"><span data-stu-id="c7144-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="c7144-133">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="c7144-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c7144-134">子元素</span><span class="sxs-lookup"><span data-stu-id="c7144-134">Child Elements</span></span>  
  
|<span data-ttu-id="c7144-135">元素</span><span class="sxs-lookup"><span data-stu-id="c7144-135">Element</span></span>|<span data-ttu-id="c7144-136">描述</span><span class="sxs-lookup"><span data-stu-id="c7144-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7144-137">\<security ></span><span class="sxs-lookup"><span data-stu-id="c7144-137">\<security></span></span>](security-of-peertransport.md)|<span data-ttu-id="c7144-138">定义此传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c7144-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="c7144-139">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="c7144-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c7144-140">父元素</span><span class="sxs-lookup"><span data-stu-id="c7144-140">Parent Elements</span></span>  
  
|<span data-ttu-id="c7144-141">元素</span><span class="sxs-lookup"><span data-stu-id="c7144-141">Element</span></span>|<span data-ttu-id="c7144-142">描述</span><span class="sxs-lookup"><span data-stu-id="c7144-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c7144-143">\<binding ></span><span class="sxs-lookup"><span data-stu-id="c7144-143">\<binding></span></span>](bindings.md)|<span data-ttu-id="c7144-144">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="c7144-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7144-145">备注</span><span class="sxs-lookup"><span data-stu-id="c7144-145">Remarks</span></span>  
 <span data-ttu-id="c7144-146">此传输不可用于包含请求/答复操作的协定。</span><span class="sxs-lookup"><span data-stu-id="c7144-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7144-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7144-147">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c7144-148">传输</span><span class="sxs-lookup"><span data-stu-id="c7144-148">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="c7144-149">选择传输</span><span class="sxs-lookup"><span data-stu-id="c7144-149">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c7144-150">绑定</span><span class="sxs-lookup"><span data-stu-id="c7144-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c7144-151">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="c7144-151">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c7144-152">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="c7144-152">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c7144-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c7144-153">\<customBinding></span></span>](custombinding.md)
