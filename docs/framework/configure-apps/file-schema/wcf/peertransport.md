---
title: '&lt;t&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6fb60d901d498c6db194e60a9229c0d5b69eee31
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltpeertransportgt"></a><span data-ttu-id="dde5b-102">&lt;t&gt;</span><span class="sxs-lookup"><span data-stu-id="dde5b-102">&lt;peerTransport&gt;</span></span>
<span data-ttu-id="dde5b-103">定义自定义绑定的对等传输。</span><span class="sxs-lookup"><span data-stu-id="dde5b-103">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="dde5b-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="dde5b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dde5b-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="dde5b-105">\<bindings></span></span>  
<span data-ttu-id="dde5b-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dde5b-106">\<customBinding></span></span>  
<span data-ttu-id="dde5b-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="dde5b-107">\<binding></span></span>  
<span data-ttu-id="dde5b-108">\<t ></span><span class="sxs-lookup"><span data-stu-id="dde5b-108">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde5b-109">语法</span><span class="sxs-lookup"><span data-stu-id="dde5b-109">Syntax</span></span>  
  
```xml  
<peerTransport   
    listenIpAddress="String"  
    maxBufferPoolSize="Integer"  
    maxReceivedMessageSize="Integer"  
    port="Integer"  
        <security>  
    </security>  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dde5b-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="dde5b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dde5b-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="dde5b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dde5b-112">特性</span><span class="sxs-lookup"><span data-stu-id="dde5b-112">Attributes</span></span>  
  
|<span data-ttu-id="dde5b-113">特性</span><span class="sxs-lookup"><span data-stu-id="dde5b-113">Attribute</span></span>|<span data-ttu-id="dde5b-114">描述</span><span class="sxs-lookup"><span data-stu-id="dde5b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dde5b-115">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="dde5b-115">listenIpAddress</span></span>|<span data-ttu-id="dde5b-116">一个字符串，指定对等节点将在其上侦听 TCP 消息的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="dde5b-116">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="dde5b-117">默认值为 `null`。</span><span class="sxs-lookup"><span data-stu-id="dde5b-117">The default is `null`.</span></span>|  
|<span data-ttu-id="dde5b-118">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="dde5b-118">maxBufferPoolSize</span></span>|<span data-ttu-id="dde5b-119">一个正整数，指定缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="dde5b-119">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="dde5b-120">默认值为 524288。</span><span class="sxs-lookup"><span data-stu-id="dde5b-120">The default is 524288.</span></span><br /><br /> <span data-ttu-id="dde5b-121">WCF 的许多组件使用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="dde5b-121">Many parts of WCF use buffers.</span></span> <span data-ttu-id="dde5b-122">每次使用缓冲区时，创建和销毁它们都将占用大量资源，而缓冲区的垃圾回收过程也是如此。</span><span class="sxs-lookup"><span data-stu-id="dde5b-122">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="dde5b-123">利用缓冲池，可以从缓冲池中获得缓冲区，使用缓冲区，然后在完成工作后将其返回给缓冲池。</span><span class="sxs-lookup"><span data-stu-id="dde5b-123">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="dde5b-124">这样就避免了创建和销毁缓冲区的系统开销。</span><span class="sxs-lookup"><span data-stu-id="dde5b-124">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="dde5b-125">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="dde5b-125">maxReceivedMessageSize</span></span>|<span data-ttu-id="dde5b-126">一个正整数，定义包括标头在内的最大消息大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="dde5b-126">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="dde5b-127">如果消息对于接收方而言太大，则消息发送方将收到 SOAP 错误。</span><span class="sxs-lookup"><span data-stu-id="dde5b-127">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="dde5b-128">接收方将删除该消息，并在跟踪日志中创建事件项。</span><span class="sxs-lookup"><span data-stu-id="dde5b-128">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="dde5b-129">默认值为 65536。</span><span class="sxs-lookup"><span data-stu-id="dde5b-129">The default is 65536.</span></span>|  
|<span data-ttu-id="dde5b-130">端口</span><span class="sxs-lookup"><span data-stu-id="dde5b-130">port</span></span>|<span data-ttu-id="dde5b-131">一个整数，指定此绑定将用于处理对等通道 TCP 消息的网络接口端口。</span><span class="sxs-lookup"><span data-stu-id="dde5b-131">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="dde5b-132">该值必须介于 <xref:System.Net.IPEndPoint.MinPort> 和 <xref:System.Net.IPEndPoint.MaxPort> 之间。</span><span class="sxs-lookup"><span data-stu-id="dde5b-132">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="dde5b-133">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="dde5b-133">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dde5b-134">子元素</span><span class="sxs-lookup"><span data-stu-id="dde5b-134">Child Elements</span></span>  
  
|<span data-ttu-id="dde5b-135">元素</span><span class="sxs-lookup"><span data-stu-id="dde5b-135">Element</span></span>|<span data-ttu-id="dde5b-136">描述</span><span class="sxs-lookup"><span data-stu-id="dde5b-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dde5b-137">\<安全 ></span><span class="sxs-lookup"><span data-stu-id="dde5b-137">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="dde5b-138">定义此传输的安全设置。</span><span class="sxs-lookup"><span data-stu-id="dde5b-138">Defines the security settings for this transport.</span></span> <span data-ttu-id="dde5b-139">此元素的类型为 <xref:System.ServiceModel.Configuration.PeerSecurityElement>。</span><span class="sxs-lookup"><span data-stu-id="dde5b-139">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dde5b-140">父元素</span><span class="sxs-lookup"><span data-stu-id="dde5b-140">Parent Elements</span></span>  
  
|<span data-ttu-id="dde5b-141">元素</span><span class="sxs-lookup"><span data-stu-id="dde5b-141">Element</span></span>|<span data-ttu-id="dde5b-142">描述</span><span class="sxs-lookup"><span data-stu-id="dde5b-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dde5b-143">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="dde5b-143">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="dde5b-144">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="dde5b-144">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde5b-145">备注</span><span class="sxs-lookup"><span data-stu-id="dde5b-145">Remarks</span></span>  
 <span data-ttu-id="dde5b-146">此传输不可用于包含请求/答复操作的协定。</span><span class="sxs-lookup"><span data-stu-id="dde5b-146">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde5b-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="dde5b-147">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerTransportElement>  
 <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="dde5b-148">传输</span><span class="sxs-lookup"><span data-stu-id="dde5b-148">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="dde5b-149">选择传输</span><span class="sxs-lookup"><span data-stu-id="dde5b-149">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="dde5b-150">绑定</span><span class="sxs-lookup"><span data-stu-id="dde5b-150">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="dde5b-151">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="dde5b-151">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="dde5b-152">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="dde5b-152">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="dde5b-153">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dde5b-153">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
