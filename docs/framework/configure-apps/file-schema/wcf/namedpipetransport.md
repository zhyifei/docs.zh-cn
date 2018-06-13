---
title: '&lt;namedPipeTransport&gt;'
ms.date: 03/30/2017
ms.assetid: 9fc3f42f-43e2-4ab1-8bc7-3c95a9220df1
ms.openlocfilehash: 652cb551fb318d43d4284dbee48aeb994f056692
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746792"
---
# <a name="ltnamedpipetransportgt"></a><span data-ttu-id="39798-102">&lt;namedPipeTransport&gt;</span><span class="sxs-lookup"><span data-stu-id="39798-102">&lt;namedPipeTransport&gt;</span></span>
<span data-ttu-id="39798-103">定义传输，使通道在被包括到自定义绑定中时使用命名管道来传输消息。</span><span class="sxs-lookup"><span data-stu-id="39798-103">Defines a transport that causes a channel to transfer messages using named pipes when it is included in a custom binding.</span></span>  
  
<span data-ttu-id="39798-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="39798-104">\<system.serviceModel></span></span>  
<span data-ttu-id="39798-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="39798-105">\<bindings></span></span>  
<span data-ttu-id="39798-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="39798-106">\<customBinding></span></span>  
<span data-ttu-id="39798-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="39798-107">\<binding></span></span>  
<span data-ttu-id="39798-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="39798-108">\<namePipeTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39798-109">语法</span><span class="sxs-lookup"><span data-stu-id="39798-109">Syntax</span></span>  
  
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
                          idleTimeout"TimeSpan"  
                          maxOutboundConnectionsPerEndpopint="Integer" />  
</namedPipeTransport>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39798-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="39798-110">Attributes and Elements</span></span>  
<span data-ttu-id="39798-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="39798-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39798-112">特性</span><span class="sxs-lookup"><span data-stu-id="39798-112">Attributes</span></span>  
<span data-ttu-id="39798-113">无。</span><span class="sxs-lookup"><span data-stu-id="39798-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39798-114">子元素</span><span class="sxs-lookup"><span data-stu-id="39798-114">Child Elements</span></span>  
  
|<span data-ttu-id="39798-115">元素</span><span class="sxs-lookup"><span data-stu-id="39798-115">Element</span></span>|<span data-ttu-id="39798-116">描述</span><span class="sxs-lookup"><span data-stu-id="39798-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39798-117">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="39798-117">ChannelInitializationTimeout</span></span>|<span data-ttu-id="39798-118">获取或设置<xref:System.TimeSpan>，它确定在断开前通道可处于初始化状态的最长时间。</span><span class="sxs-lookup"><span data-stu-id="39798-118">Gets or sets a <xref:System.TimeSpan> that determines the maximum time a channel can be in the initialization status before being disconnected.</span></span>|  
|<span data-ttu-id="39798-119">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="39798-119">ConnectionBufferSize</span></span>|<span data-ttu-id="39798-120">获取或设置用于从客户端或服务传输网络上的序列化消息块的缓冲区大小。</span><span class="sxs-lookup"><span data-stu-id="39798-120">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="39798-121">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="39798-121">hostNameComparisonMode</span></span>|<span data-ttu-id="39798-122">获取或设置一个值，该值指示在对 URI 进行匹配时，是否使用主机名来访问服务。</span><span class="sxs-lookup"><span data-stu-id="39798-122">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="39798-123">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="39798-123">manualAddressing</span></span>|<span data-ttu-id="39798-124">获取或设置一个值，该值指示是否要求对消息进行手动寻址。</span><span class="sxs-lookup"><span data-stu-id="39798-124">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="39798-125">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="39798-125">maxBufferPoolSize</span></span>|<span data-ttu-id="39798-126">获取或设置的最大大小，以字节为单位的传输使用任何缓冲池。</span><span class="sxs-lookup"><span data-stu-id="39798-126">Gets or sets the maximum size, in bytes, of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="39798-127">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="39798-127">maxBufferSize</span></span>|<span data-ttu-id="39798-128">获取或设置要使用的缓冲区的最大大小。</span><span class="sxs-lookup"><span data-stu-id="39798-128">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="39798-129">对于经过流处理的消息，该值最少应为以缓冲模式读取的消息头的最大可能大小。</span><span class="sxs-lookup"><span data-stu-id="39798-129">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="39798-130">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="39798-130">maxOutputDelay</span></span>|<span data-ttu-id="39798-131">获取或设置消息块或完整消息在发出之前可以在内存中保持缓冲的最大时间间隔。</span><span class="sxs-lookup"><span data-stu-id="39798-131">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="39798-132">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="39798-132">maxPendingAccepts</span></span>|<span data-ttu-id="39798-133">获取或设置最大的服务可以有用于处理传入连接到服务等待侦听器的通道数。</span><span class="sxs-lookup"><span data-stu-id="39798-133">Gets or sets the maximum number of channels a service can have waiting on a listener for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="39798-134">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="39798-134">maxPendingConnections</span></span>|<span data-ttu-id="39798-135">获取或设置在服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="39798-135">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="39798-136">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="39798-136">maxReceivedMessageSize</span></span>|<span data-ttu-id="39798-137">获取和设置的最大消息大小，以字节为单位，可以接收。</span><span class="sxs-lookup"><span data-stu-id="39798-137">Gets and sets the maximum allowable message size, in bytes, that can be received.</span></span>|  
|<span data-ttu-id="39798-138">transferMode</span><span class="sxs-lookup"><span data-stu-id="39798-138">transferMode</span></span>|<span data-ttu-id="39798-139">获取或设置一个值，该值指示通过面向连接的传输对消息进行缓冲还是流处理。</span><span class="sxs-lookup"><span data-stu-id="39798-139">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|[<span data-ttu-id="39798-140">\<connectionPoolSettings > 的\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="39798-140">\<connectionPoolSettings> of \<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/connectionpoolsettings.md)|<span data-ttu-id="39798-141">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="39798-141">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39798-142">父元素</span><span class="sxs-lookup"><span data-stu-id="39798-142">Parent Elements</span></span>  
  
|<span data-ttu-id="39798-143">元素</span><span class="sxs-lookup"><span data-stu-id="39798-143">Element</span></span>|<span data-ttu-id="39798-144">描述</span><span class="sxs-lookup"><span data-stu-id="39798-144">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39798-145">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="39798-145">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="39798-146">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="39798-146">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39798-147">备注</span><span class="sxs-lookup"><span data-stu-id="39798-147">Remarks</span></span>  
<span data-ttu-id="39798-148">此传输使用“net.pipe://hostname/path”形式的 URI。</span><span class="sxs-lookup"><span data-stu-id="39798-148">This transport uses URIs of the form "net.pipe://hostname/path".</span></span> <span data-ttu-id="39798-149">其他 URI 组件是可选的。</span><span class="sxs-lookup"><span data-stu-id="39798-149">Other URI components are optional.</span></span>  
  
<span data-ttu-id="39798-150">`namedPipeTransport` 元素是创建实现命名管道传输协议的自定义绑定的起始点。</span><span class="sxs-lookup"><span data-stu-id="39798-150">The `namedPipeTransport` element is the starting point for creating a custom binding that implements the named pipes transport protocol.</span></span> <span data-ttu-id="39798-151">此传输用于计算机上的 WCF (Windows Communication Foundation) 到 WCF 的通信。</span><span class="sxs-lookup"><span data-stu-id="39798-151">This transport is used for on-machine Windows Communication Foundation (WCF)-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39798-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="39798-152">See Also</span></span>  
<xref:System.ServiceModel.Configuration.NamedPipeTransportElement>   
<xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>   
<xref:System.ServiceModel.Channels.TransportBindingElement>   
<xref:System.ServiceModel.Channels.CustomBinding>   
<span data-ttu-id="39798-153">[传输](../../../../../docs/framework/wcf/feature-details/transports.md) </span><span class="sxs-lookup"><span data-stu-id="39798-153">[Transports](../../../../../docs/framework/wcf/feature-details/transports.md) </span></span>  
<span data-ttu-id="39798-154">[选择传输](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span><span class="sxs-lookup"><span data-stu-id="39798-154">[Choosing a Transport](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md) </span></span>  
<span data-ttu-id="39798-155">[绑定](../../../../../docs/framework/wcf/bindings.md) </span><span class="sxs-lookup"><span data-stu-id="39798-155">[Bindings](../../../../../docs/framework/wcf/bindings.md) </span></span>  
<span data-ttu-id="39798-156">[扩展绑定](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="39798-156">[Extending Bindings](../../../../../docs/framework/wcf/extending/extending-bindings.md) </span></span>  
<span data-ttu-id="39798-157">[自定义绑定](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span><span class="sxs-lookup"><span data-stu-id="39798-157">[Custom Bindings](../../../../../docs/framework/wcf/extending/custom-bindings.md) </span></span>  
[<span data-ttu-id="39798-158">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="39798-158">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
