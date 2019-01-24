---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: cdb2863ff376a92f7c4b679f4812b895ac3f2234
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518834"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="9a1ad-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="9a1ad-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="9a1ad-103">定义传输，使通道在被包括到自定义绑定中时使用命名管道来传输消息。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="9a1ad-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9a1ad-104">\<system.serviceModel></span></span>  
<span data-ttu-id="9a1ad-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9a1ad-105">\<bindings></span></span>  
<span data-ttu-id="9a1ad-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9a1ad-106">\<customBinding></span></span>  
<span data-ttu-id="9a1ad-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a1ad-107">\<binding></span></span>  
<span data-ttu-id="9a1ad-108">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="9a1ad-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a1ad-109">语法</span><span class="sxs-lookup"><span data-stu-id="9a1ad-109">Syntax</span></span>  
  
```xml  
<namedPipeTransport channelInitializationTimeout="TimeSpan"
                    connectionBufferSize="Integer"
                    hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
                    manualAddressing="Boolean"
                    maxBufferPoolSize="Integer"
                    maxBufferSize="Integer"
                    maxOutputDelay="TimeSpan"
                    maxPendingAccepts="Integer"
                    maxPendingConnections="Integer"
                    maxReceivedMessageSize="Integer"
                    transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse">
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a1ad-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9a1ad-110">Attributes and Elements</span></span>  
<span data-ttu-id="9a1ad-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a1ad-112">特性</span><span class="sxs-lookup"><span data-stu-id="9a1ad-112">Attributes</span></span>  
<span data-ttu-id="9a1ad-113">无。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a1ad-114">子元素</span><span class="sxs-lookup"><span data-stu-id="9a1ad-114">Child Elements</span></span>  
  
|<span data-ttu-id="9a1ad-115">元素</span><span class="sxs-lookup"><span data-stu-id="9a1ad-115">Element</span></span>|<span data-ttu-id="9a1ad-116">描述</span><span class="sxs-lookup"><span data-stu-id="9a1ad-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a1ad-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="9a1ad-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="9a1ad-118">获取或设置<xref:System.TimeSpan>，它确定在断开连接前通道可处于初始化状态的最长时间。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="9a1ad-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="9a1ad-119">ConnectionBufferSize</span></span>|<span data-ttu-id="9a1ad-120">获取或设置用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="9a1ad-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="9a1ad-121">hostNameComparisonMode</span></span>|<span data-ttu-id="9a1ad-122">获取或设置一个值，该值指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="9a1ad-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="9a1ad-123">manualAddressing</span></span>|<span data-ttu-id="9a1ad-124">获取或设置一个值，该值指示是否要求对消息进行手动寻址。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="9a1ad-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="9a1ad-125">maxBufferPoolSize</span></span>|<span data-ttu-id="9a1ad-126">获取或设置最大大小，以字节为任何的单位传输使用的缓冲池。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="9a1ad-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="9a1ad-127">maxBufferSize</span></span>|<span data-ttu-id="9a1ad-128">获取或设置要使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="9a1ad-129">对于经过流处理的消息，该值最少应为以缓冲模式读取的消息头的最大可能大小。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="9a1ad-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="9a1ad-130">maxOutputDelay</span></span>|<span data-ttu-id="9a1ad-131">获取或设置消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="9a1ad-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="9a1ad-132">maxPendingAccepts</span></span>|<span data-ttu-id="9a1ad-133">获取或设置一个服务可以有一个侦听器上等待用于处理传入连接到服务的通道的最大数目。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="9a1ad-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="9a1ad-134">maxPendingConnections</span></span>|<span data-ttu-id="9a1ad-135">获取或设置在服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="9a1ad-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="9a1ad-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="9a1ad-137">获取和设置最大消息大小，以字节为单位，可以接收。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="9a1ad-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="9a1ad-138">transferMode</span></span>|<span data-ttu-id="9a1ad-139">获取或设置一个值，该值指示通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="9a1ad-140">\<connectionPoolSettings> of \<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="9a1ad-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="9a1ad-141">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a1ad-142">父元素</span><span class="sxs-lookup"><span data-stu-id="9a1ad-142">Parent Elements</span></span>  
  
|<span data-ttu-id="9a1ad-143">元素</span><span class="sxs-lookup"><span data-stu-id="9a1ad-143">Element</span></span>|<span data-ttu-id="9a1ad-144">描述</span><span class="sxs-lookup"><span data-stu-id="9a1ad-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9a1ad-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="9a1ad-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9a1ad-146">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a1ad-147">备注</span><span class="sxs-lookup"><span data-stu-id="9a1ad-147">Remarks</span></span>  
<span data-ttu-id="9a1ad-148">此传输使用“net.pipe://hostname/path”形式的 URI。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="9a1ad-149">其他 URI 组件是可选的。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="9a1ad-150">`namedPipeTransport` 元素是创建实现命名管道传输协议的自定义绑定的起始点。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="9a1ad-151">此传输用于计算机上的 WCF (Windows Communication Foundation) 到 WCF 的通信。</span><span class="sxs-lookup"><span data-stu-id="9a1ad-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1ad-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a1ad-152">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9a1ad-153">传输</span><span class="sxs-lookup"><span data-stu-id="9a1ad-153">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="9a1ad-154">选择传输</span><span class="sxs-lookup"><span data-stu-id="9a1ad-154">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="9a1ad-155">绑定</span><span class="sxs-lookup"><span data-stu-id="9a1ad-155">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9a1ad-156">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="9a1ad-156">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9a1ad-157">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="9a1ad-157">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9a1ad-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9a1ad-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
