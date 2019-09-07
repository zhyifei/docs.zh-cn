---
title: <namedPipeTransport>
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: e5f1d49e0e3bb5f52c5e18577d556d25539434a9
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400165"
---
# <a name="namedpipetransport"></a><span data-ttu-id="710c9-101">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="710c9-101">\<namedPipeTransport></span></span>
<span data-ttu-id="710c9-102">定义传输，使通道在被包括到自定义绑定中时使用命名管道来传输消息。</span><span class="sxs-lookup"><span data-stu-id="710c9-102">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="710c9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="710c9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="710c9-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="710c9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="710c9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="710c9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="710c9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="710c9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="710c9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="710c9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="710c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<namedPipeTransport >**</span><span class="sxs-lookup"><span data-stu-id="710c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namedPipeTransport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="710c9-109">语法</span><span class="sxs-lookup"><span data-stu-id="710c9-109">Syntax</span></span>  
  
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
                          maxOutboundConnectionsPerEndpoint="Integer" />
</namedPipeTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="710c9-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="710c9-110">Attributes and Elements</span></span>  
<span data-ttu-id="710c9-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="710c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="710c9-112">特性</span><span class="sxs-lookup"><span data-stu-id="710c9-112">Attributes</span></span>  
<span data-ttu-id="710c9-113">无。</span><span class="sxs-lookup"><span data-stu-id="710c9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="710c9-114">子元素</span><span class="sxs-lookup"><span data-stu-id="710c9-114">Child Elements</span></span>  
  
|<span data-ttu-id="710c9-115">元素</span><span class="sxs-lookup"><span data-stu-id="710c9-115">Element</span></span>|<span data-ttu-id="710c9-116">描述</span><span class="sxs-lookup"><span data-stu-id="710c9-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="710c9-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="710c9-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="710c9-118">获取或设置一个<xref:System.TimeSpan> ，它确定通道在断开连接前可处于初始化状态的最大时间。</span><span class="sxs-lookup"><span data-stu-id="710c9-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="710c9-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="710c9-119">ConnectionBufferSize</span></span>|<span data-ttu-id="710c9-120">获取或设置用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="710c9-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="710c9-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="710c9-121">hostNameComparisonMode</span></span>|<span data-ttu-id="710c9-122">获取或设置一个值，该值指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="710c9-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="710c9-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="710c9-123">manualAddressing</span></span>|<span data-ttu-id="710c9-124">获取或设置一个值，该值指示是否要求对消息进行手动寻址。</span><span class="sxs-lookup"><span data-stu-id="710c9-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="710c9-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="710c9-125">maxBufferPoolSize</span></span>|<span data-ttu-id="710c9-126">获取或设置传输使用的任何缓冲池的最大大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="710c9-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="710c9-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="710c9-127">maxBufferSize</span></span>|<span data-ttu-id="710c9-128">获取或设置要使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="710c9-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="710c9-129">对于经过流处理的消息，该值最少应为以缓冲模式读取的消息头的最大可能大小。</span><span class="sxs-lookup"><span data-stu-id="710c9-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="710c9-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="710c9-130">maxOutputDelay</span></span>|<span data-ttu-id="710c9-131">获取或设置消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="710c9-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="710c9-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="710c9-132">maxPendingAccepts</span></span>|<span data-ttu-id="710c9-133">获取或设置服务在侦听器上等待处理到服务的传入连接的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="710c9-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="710c9-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="710c9-134">maxPendingConnections</span></span>|<span data-ttu-id="710c9-135">获取或设置在服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="710c9-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="710c9-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="710c9-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="710c9-137">获取和设置允许接收的最大消息大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="710c9-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="710c9-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="710c9-138">transferMode</span></span>|<span data-ttu-id="710c9-139">获取或设置一个值，该值指示通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="710c9-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="710c9-140">\<connectionPoolSettings > \<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="710c9-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](connectionpoolsettings.md)|<span data-ttu-id="710c9-141">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="710c9-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="710c9-142">父元素</span><span class="sxs-lookup"><span data-stu-id="710c9-142">Parent Elements</span></span>  
  
|<span data-ttu-id="710c9-143">元素</span><span class="sxs-lookup"><span data-stu-id="710c9-143">Element</span></span>|<span data-ttu-id="710c9-144">描述</span><span class="sxs-lookup"><span data-stu-id="710c9-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="710c9-145">\<binding></span><span class="sxs-lookup"><span data-stu-id="710c9-145">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="710c9-146">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="710c9-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="710c9-147">备注</span><span class="sxs-lookup"><span data-stu-id="710c9-147">Remarks</span></span>  
<span data-ttu-id="710c9-148">此传输使用“net.pipe://hostname/path”形式的 URI。</span><span class="sxs-lookup"><span data-stu-id="710c9-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="710c9-149">其他 URI 组件是可选的。</span><span class="sxs-lookup"><span data-stu-id="710c9-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="710c9-150">`namedPipeTransport` 元素是创建实现命名管道传输协议的自定义绑定的起始点。</span><span class="sxs-lookup"><span data-stu-id="710c9-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="710c9-151">此传输用于计算机上的 WCF (Windows Communication Foundation) 到 WCF 的通信。</span><span class="sxs-lookup"><span data-stu-id="710c9-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="710c9-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="710c9-152">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeTransportElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="710c9-153">传输</span><span class="sxs-lookup"><span data-stu-id="710c9-153">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="710c9-154">选择传输</span><span class="sxs-lookup"><span data-stu-id="710c9-154">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="710c9-155">绑定</span><span class="sxs-lookup"><span data-stu-id="710c9-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="710c9-156">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="710c9-156">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="710c9-157">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="710c9-157">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="710c9-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="710c9-158">\<customBinding></span></span>](custombinding.md)
