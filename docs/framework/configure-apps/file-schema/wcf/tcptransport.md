---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 6c5bb61f234c8d5b8ffc5e16195a2cb50022d142
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166161"
---
# <a name="tcptransport"></a><span data-ttu-id="5f1c2-101">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="5f1c2-101">\<tcpTransport></span></span>
<span data-ttu-id="5f1c2-102">定义通道用于传输自定义绑定消息的 TCP 传输。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-102">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
 <span data-ttu-id="5f1c2-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5f1c2-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5f1c2-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5f1c2-104">\<bindings></span></span>  
<span data-ttu-id="5f1c2-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5f1c2-105">\<customBinding></span></span>  
<span data-ttu-id="5f1c2-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5f1c2-106">\<binding></span></span>  
<span data-ttu-id="5f1c2-107">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="5f1c2-107">\<tcpTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f1c2-108">语法</span><span class="sxs-lookup"><span data-stu-id="5f1c2-108">Syntax</span></span>  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5f1c2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5f1c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5f1c2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5f1c2-111">特性</span><span class="sxs-lookup"><span data-stu-id="5f1c2-111">Attributes</span></span>  
  
|<span data-ttu-id="5f1c2-112">特性</span><span class="sxs-lookup"><span data-stu-id="5f1c2-112">Attribute</span></span>|<span data-ttu-id="5f1c2-113">描述</span><span class="sxs-lookup"><span data-stu-id="5f1c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5f1c2-114">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="5f1c2-114">channelInitializationTimeout</span></span>|<span data-ttu-id="5f1c2-115">获取或设置对要接受的通道进行初始化的时间限制。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-115">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="5f1c2-116">通道在断开连接前可处于初始化状态的最长时间（秒）。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-116">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="5f1c2-117">此配额包括 TCP 连接可能需要进行身份验证使用.NET Message Framing 协议本身的时间。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-117">This quota includes the time a TCP connection can take to authenticate itself using the .NET Message Framing protocol.</span></span> <span data-ttu-id="5f1c2-118">客户端需要发送一些初始数据，然后服务器才有足够的信息来执行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-118">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="5f1c2-119">默认值为 30 秒。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-119">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="5f1c2-120">connectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="5f1c2-120">connectionBufferSize</span></span>|<span data-ttu-id="5f1c2-121">获取或设置用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-121">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="5f1c2-122">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="5f1c2-122">hostNameComparisonMode</span></span>|<span data-ttu-id="5f1c2-123">获取或设置一个值，该值指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-123">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="5f1c2-124">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="5f1c2-124">listenBacklog</span></span>|<span data-ttu-id="5f1c2-125">可为 Web 服务挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-125">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="5f1c2-126">`connectionLeaseTimeout` 属性限制客户端在引发连接异常之前将等待连接的持续时间。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-126">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="5f1c2-127">这是一个套接字级别属性，控制可能为 Web 服务挂起的最大排队连接请求数。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-127">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="5f1c2-128">ListenBacklog 太低时，WCF 将停止接受请求并因此删除新连接，直到服务器确认一些现有队列连接。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-128">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections.</span></span> <span data-ttu-id="5f1c2-129">默认值为 16 \* 处理器数。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-129">The default is 16 \* number of processors.</span></span>|  
|<span data-ttu-id="5f1c2-130">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="5f1c2-130">manualAddressing</span></span>|<span data-ttu-id="5f1c2-131">获取或设置一个值，该值指示是否要求对消息进行手动寻址。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-131">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="5f1c2-132">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="5f1c2-132">maxBufferPoolSize</span></span>|<span data-ttu-id="5f1c2-133">获取或设置传输使用的任何缓冲池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-133">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="5f1c2-134">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="5f1c2-134">maxBufferSize</span></span>|<span data-ttu-id="5f1c2-135">获取或设置要使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-135">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="5f1c2-136">对于经过流处理的消息，该值最少应为以缓冲模式读取的消息头的最大可能大小。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-136">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="5f1c2-137">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="5f1c2-137">maxOutputDelay</span></span>|<span data-ttu-id="5f1c2-138">获取或设置消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-138">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="5f1c2-139">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="5f1c2-139">maxPendingAccepts</span></span>|<span data-ttu-id="5f1c2-140">获取或设置可用于处理服务上的传入连接的最大挂起异步接受操作数。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-140">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="5f1c2-141">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="5f1c2-141">maxPendingConnections</span></span>|<span data-ttu-id="5f1c2-142">获取或设置在服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-142">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="5f1c2-143">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="5f1c2-143">maxReceivedMessageSize</span></span>|<span data-ttu-id="5f1c2-144">获取和设置允许接收的最大消息大小。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-144">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="5f1c2-145">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="5f1c2-145">portSharingEnabled</span></span>|<span data-ttu-id="5f1c2-146">一个布尔值，指定是否为此连接启用 TCP 端口共享。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-146">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="5f1c2-147">如果此值为 `false`，则每个绑定都将使用自己的独占端口。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-147">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="5f1c2-148">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-148">The default is `false`.</span></span><br /><br /> <span data-ttu-id="5f1c2-149">此设置只与服务相关。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-149">This setting is relevant only to services.</span></span> <span data-ttu-id="5f1c2-150">客户端并不会受影响。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-150">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="5f1c2-151">使用此设置要求通过将 Windows Communication Foundation (WCF) TCP 端口共享服务的“启动类型”设置为“手动”或“自动”来启用该服务。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-151">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="5f1c2-152">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="5f1c2-152">teredoEnabled</span></span>|<span data-ttu-id="5f1c2-153">一个布尔值，指定是否启用 Teredo（一种用于对防火墙后的客户端进行寻址的技术）。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-153">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="5f1c2-154">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-154">The default is `false`.</span></span><br /><br /> <span data-ttu-id="5f1c2-155">此属性为基础 TCP 套接字启用 Teredo。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-155">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="5f1c2-156">有关详细信息，请参阅[Teredo 概述](https://go.microsoft.com/fwlink/?LinkId=95339)。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-156">For more information, see [Teredo Overview](https://go.microsoft.com/fwlink/?LinkId=95339).</span></span><br /><br /> <span data-ttu-id="5f1c2-157">此属性仅适用于 [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] 和 [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-157">This property is applicable only on [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] and [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)].</span></span> [!INCLUDE[wv](../../../../../includes/wv-md.md)] <span data-ttu-id="5f1c2-158">具有用于 Teredo 的计算机范围的配置选项，因此运行 Vista 时将忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-158">has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="5f1c2-159">Teredo 要求客户端和服务计算机都安装 Microsoft IPv6 堆栈，并进行正确的配置以便使用 Teredo。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-159">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span> <span data-ttu-id="5f1c2-160">有关配置 Teredo 的详细信息，请参阅[Teredo 概述](https://go.microsoft.com/fwlink/?LinkId=95339)。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-160">For more information about configuring Teredo, see [Teredo Overview](https://go.microsoft.com/fwlink/?LinkId=95339).</span></span> <span data-ttu-id="5f1c2-161">有关详细信息，请参阅[Windows Server 2003 技术中心](https://go.microsoft.com/fwlink/?LinkId=49888)。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-161">For more information, see [Windows Server 2003 Technology Centers](https://go.microsoft.com/fwlink/?LinkId=49888).</span></span>|  
|<span data-ttu-id="5f1c2-162">transferMode</span><span class="sxs-lookup"><span data-stu-id="5f1c2-162">transferMode</span></span>|<span data-ttu-id="5f1c2-163">获取或设置一个值，该值指示通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-163">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="5f1c2-164">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="5f1c2-164">connectionPoolSettings</span></span>|<span data-ttu-id="5f1c2-165">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-165">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5f1c2-166">子元素</span><span class="sxs-lookup"><span data-stu-id="5f1c2-166">Child Elements</span></span>  
 <span data-ttu-id="5f1c2-167">None</span><span class="sxs-lookup"><span data-stu-id="5f1c2-167">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5f1c2-168">父元素</span><span class="sxs-lookup"><span data-stu-id="5f1c2-168">Parent Elements</span></span>  
  
|<span data-ttu-id="5f1c2-169">元素</span><span class="sxs-lookup"><span data-stu-id="5f1c2-169">Element</span></span>|<span data-ttu-id="5f1c2-170">描述</span><span class="sxs-lookup"><span data-stu-id="5f1c2-170">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5f1c2-171">\<binding></span><span class="sxs-lookup"><span data-stu-id="5f1c2-171">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="5f1c2-172">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-172">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f1c2-173">备注</span><span class="sxs-lookup"><span data-stu-id="5f1c2-173">Remarks</span></span>  
 <span data-ttu-id="5f1c2-174">此传输使用“net.tcp://hostname:port/path”形式的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-174">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="5f1c2-175">其他 URI 组件是可选的。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-175">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="5f1c2-176">`tcpTransport` 元素是创建实现 TCP 传输协议的自定义绑定的起始点。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-176">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="5f1c2-177">针对 WCF 到 WCF 的通信对此传输进行了优化。</span><span class="sxs-lookup"><span data-stu-id="5f1c2-177">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f1c2-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f1c2-178">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5f1c2-179">传输</span><span class="sxs-lookup"><span data-stu-id="5f1c2-179">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="5f1c2-180">选择传输</span><span class="sxs-lookup"><span data-stu-id="5f1c2-180">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="5f1c2-181">绑定</span><span class="sxs-lookup"><span data-stu-id="5f1c2-181">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="5f1c2-182">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="5f1c2-182">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5f1c2-183">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="5f1c2-183">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5f1c2-184">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5f1c2-184">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
