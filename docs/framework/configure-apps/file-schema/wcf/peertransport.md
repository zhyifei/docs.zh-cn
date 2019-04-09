---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 6765259f290047a4199a422b4ad0cced2ffee9ae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179824"
---
# <a name="peertransport"></a><span data-ttu-id="01f6c-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="01f6c-101">\<peerTransport></span></span>
<span data-ttu-id="01f6c-102">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="01f6c-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="01f6c-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="01f6c-103">\<system.serviceModel></span></span>  
<span data-ttu-id="01f6c-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="01f6c-104">\<bindings></span></span>  
<span data-ttu-id="01f6c-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="01f6c-105">\<customBinding></span></span>  
<span data-ttu-id="01f6c-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="01f6c-106">\<binding></span></span>  
<span data-ttu-id="01f6c-107">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="01f6c-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01f6c-108">语法</span><span class="sxs-lookup"><span data-stu-id="01f6c-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01f6c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="01f6c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01f6c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="01f6c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01f6c-111">特性</span><span class="sxs-lookup"><span data-stu-id="01f6c-111">Attributes</span></span>  
  
|<span data-ttu-id="01f6c-112">特性</span><span class="sxs-lookup"><span data-stu-id="01f6c-112">Attribute</span></span>|<span data-ttu-id="01f6c-113">描述</span><span class="sxs-lookup"><span data-stu-id="01f6c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01f6c-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="01f6c-114">listenIpAddress</span></span>|<span data-ttu-id="01f6c-115">一个字符串，指定对等节点将在其上侦听 TCP 消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="01f6c-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="01f6c-116">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="01f6c-116">The default is `null`.</span></span>|  
|<span data-ttu-id="01f6c-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="01f6c-117">maxBufferPoolSize</span></span>|<span data-ttu-id="01f6c-118">一个正整数，指定缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="01f6c-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="01f6c-119">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="01f6c-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="01f6c-120">WCF 的许多组件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="01f6c-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="01f6c-121">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="01f6c-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="01f6c-122">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="01f6c-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="01f6c-123">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="01f6c-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="01f6c-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="01f6c-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="01f6c-125">一个正整数，定义包括标头在内的最大消息大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="01f6c-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="01f6c-126">如果消息对于接收方而言太大，则消息发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="01f6c-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="01f6c-127">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="01f6c-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="01f6c-128">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="01f6c-128">The default is 65536.</span></span>|  
|<span data-ttu-id="01f6c-129">端口</span><span class="sxs-lookup"><span data-stu-id="01f6c-129">port</span></span>|<span data-ttu-id="01f6c-130">一个整数，指定此绑定将用于处理对等通道 TCP 消息的网络接口端口。</span><span class="sxs-lookup"><span data-stu-id="01f6c-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="01f6c-131">该值必须介于 <xref:System.Net.IPEndPoint.MinPort> 和 <xref:System.Net.IPEndPoint.MaxPort> 之间。</span><span class="sxs-lookup"><span data-stu-id="01f6c-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="01f6c-132">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="01f6c-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01f6c-133">子元素</span><span class="sxs-lookup"><span data-stu-id="01f6c-133">Child Elements</span></span>  
  
|<span data-ttu-id="01f6c-134">元素</span><span class="sxs-lookup"><span data-stu-id="01f6c-134">Element</span></span>|<span data-ttu-id="01f6c-135">描述</span><span class="sxs-lookup"><span data-stu-id="01f6c-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01f6c-136">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="01f6c-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="01f6c-137">定义此传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="01f6c-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="01f6c-138">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="01f6c-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01f6c-139">父元素</span><span class="sxs-lookup"><span data-stu-id="01f6c-139">Parent Elements</span></span>  
  
|<span data-ttu-id="01f6c-140">元素</span><span class="sxs-lookup"><span data-stu-id="01f6c-140">Element</span></span>|<span data-ttu-id="01f6c-141">描述</span><span class="sxs-lookup"><span data-stu-id="01f6c-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01f6c-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="01f6c-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="01f6c-143">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="01f6c-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01f6c-144">备注</span><span class="sxs-lookup"><span data-stu-id="01f6c-144">Remarks</span></span>  
 <span data-ttu-id="01f6c-145">此传输不可用于包含请求/答复操作的协定。</span><span class="sxs-lookup"><span data-stu-id="01f6c-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01f6c-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="01f6c-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="01f6c-147">传输</span><span class="sxs-lookup"><span data-stu-id="01f6c-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="01f6c-148">选择传输方式</span><span class="sxs-lookup"><span data-stu-id="01f6c-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="01f6c-149">绑定</span><span class="sxs-lookup"><span data-stu-id="01f6c-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="01f6c-150">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="01f6c-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="01f6c-151">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="01f6c-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="01f6c-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="01f6c-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
