---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: e30fcd5952fadc3b6cf30cb352a3bb51c86cc117
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285894"
---
# <a name="namedpipetransport"></a><span data-ttu-id="074fe-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="074fe-101">\<namedPipeTransport></span></span>
<span data-ttu-id="074fe-102">定义传输，使通道在被包括到自定义绑定中时使用命名管道来传输消息。</span><span class="sxs-lookup"><span data-stu-id="074fe-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="074fe-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="074fe-103">\<system.serviceModel></span></span>  
<span data-ttu-id="074fe-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="074fe-104">\<bindings></span></span>  
<span data-ttu-id="074fe-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="074fe-105">\<customBinding></span></span>  
<span data-ttu-id="074fe-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="074fe-106">\<binding></span></span>  
<span data-ttu-id="074fe-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="074fe-107">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="074fe-108">语法</span><span class="sxs-lookup"><span data-stu-id="074fe-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="074fe-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="074fe-109">Attributes and Elements</span></span>  
<span data-ttu-id="074fe-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="074fe-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="074fe-111">特性</span><span class="sxs-lookup"><span data-stu-id="074fe-111">Attributes</span></span>  
<span data-ttu-id="074fe-112">无。</span><span class="sxs-lookup"><span data-stu-id="074fe-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="074fe-113">子元素</span><span class="sxs-lookup"><span data-stu-id="074fe-113">Child Elements</span></span>  
  
|<span data-ttu-id="074fe-114">元素</span><span class="sxs-lookup"><span data-stu-id="074fe-114">Element</span></span>|<span data-ttu-id="074fe-115">描述</span><span class="sxs-lookup"><span data-stu-id="074fe-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="074fe-116">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="074fe-116">ChannelInitializationTimeout</span></span>|<span data-ttu-id="074fe-117">获取或设置<xref:System.TimeSpan>，它确定在断开连接前通道可处于初始化状态的最长时间。</span><span class="sxs-lookup"><span data-stu-id="074fe-117">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="074fe-118">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="074fe-118">ConnectionBufferSize</span></span>|<span data-ttu-id="074fe-119">获取或设置用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="074fe-119">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="074fe-120">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="074fe-120">hostNameComparisonMode</span></span>|<span data-ttu-id="074fe-121">获取或设置一个值，该值指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="074fe-121">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="074fe-122">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="074fe-122">manualAddressing</span></span>|<span data-ttu-id="074fe-123">获取或设置一个值，该值指示是否要求对消息进行手动寻址。</span><span class="sxs-lookup"><span data-stu-id="074fe-123">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="074fe-124">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="074fe-124">maxBufferPoolSize</span></span>|<span data-ttu-id="074fe-125">获取或设置最大大小，以字节为任何的单位传输使用的缓冲池。</span><span class="sxs-lookup"><span data-stu-id="074fe-125">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="074fe-126">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="074fe-126">maxBufferSize</span></span>|<span data-ttu-id="074fe-127">获取或设置要使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="074fe-127">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="074fe-128">对于经过流处理的消息，该值最少应为以缓冲模式读取的消息头的最大可能大小。</span><span class="sxs-lookup"><span data-stu-id="074fe-128">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="074fe-129">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="074fe-129">maxOutputDelay</span></span>|<span data-ttu-id="074fe-130">获取或设置消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="074fe-130">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="074fe-131">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="074fe-131">maxPendingAccepts</span></span>|<span data-ttu-id="074fe-132">获取或设置一个服务可以有一个侦听器上等待用于处理传入连接到服务的通道的最大数目。</span><span class="sxs-lookup"><span data-stu-id="074fe-132">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="074fe-133">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="074fe-133">maxPendingConnections</span></span>|<span data-ttu-id="074fe-134">获取或设置在服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="074fe-134">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="074fe-135">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="074fe-135">maxReceivedMessageSize</span></span>|<span data-ttu-id="074fe-136">获取和设置最大消息大小，以字节为单位，可以接收。</span><span class="sxs-lookup"><span data-stu-id="074fe-136">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="074fe-137">transferMode</span><span class="sxs-lookup"><span data-stu-id="074fe-137">transferMode</span></span>|<span data-ttu-id="074fe-138">获取或设置一个值，该值指示通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="074fe-138">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="074fe-139">\<connectionPoolSettings> of \<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="074fe-139">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="074fe-140">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="074fe-140">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="074fe-141">父元素</span><span class="sxs-lookup"><span data-stu-id="074fe-141">Parent Elements</span></span>  
  
|<span data-ttu-id="074fe-142">元素</span><span class="sxs-lookup"><span data-stu-id="074fe-142">Element</span></span>|<span data-ttu-id="074fe-143">描述</span><span class="sxs-lookup"><span data-stu-id="074fe-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="074fe-144">\<binding></span><span class="sxs-lookup"><span data-stu-id="074fe-144">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="074fe-145">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="074fe-145">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="074fe-146">备注</span><span class="sxs-lookup"><span data-stu-id="074fe-146">Remarks</span></span>  
<span data-ttu-id="074fe-147">此传输使用“net.pipe://hostname/path”形式的 URI。</span><span class="sxs-lookup"><span data-stu-id="074fe-147">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="074fe-148">其他 URI 组件是可选的。</span><span class="sxs-lookup"><span data-stu-id="074fe-148">Other URI components are optional.</span></span>  
  
<span data-ttu-id="074fe-149">`namedPipeTransport` 元素是创建实现命名管道传输协议的自定义绑定的起始点。</span><span class="sxs-lookup"><span data-stu-id="074fe-149">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="074fe-150">此传输用于计算机上的 WCF (Windows Communication Foundation) 到 WCF 的通信。</span><span class="sxs-lookup"><span data-stu-id="074fe-150">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="074fe-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="074fe-151">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="074fe-152">传输</span><span class="sxs-lookup"><span data-stu-id="074fe-152">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="074fe-153">选择传输</span><span class="sxs-lookup"><span data-stu-id="074fe-153">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="074fe-154">绑定</span><span class="sxs-lookup"><span data-stu-id="074fe-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="074fe-155">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="074fe-155">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="074fe-156">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="074fe-156">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="074fe-157">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="074fe-157">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
