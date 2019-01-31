---
title: <connectionPoolSettings> 的 <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 4828357f392089be14ee04bc672acce0c0973300
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269258"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="40c94-102">\<connectionPoolSettings> of \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="40c94-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="40c94-103">指定 TCP 传输的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="40c94-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="40c94-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="40c94-104">\<system.serviceModel></span></span>  
<span data-ttu-id="40c94-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="40c94-105">\<bindings></span></span>  
<span data-ttu-id="40c94-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="40c94-106">\<customBinding></span></span>  
<span data-ttu-id="40c94-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="40c94-107">\<binding></span></span>  
<span data-ttu-id="40c94-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="40c94-108">\<tcpTransport></span></span>  
<span data-ttu-id="40c94-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="40c94-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40c94-110">语法</span><span class="sxs-lookup"><span data-stu-id="40c94-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40c94-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40c94-111">Attributes and Elements</span></span>  
 <span data-ttu-id="40c94-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40c94-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40c94-113">特性</span><span class="sxs-lookup"><span data-stu-id="40c94-113">Attributes</span></span>  
  
|<span data-ttu-id="40c94-114">特性</span><span class="sxs-lookup"><span data-stu-id="40c94-114">Attribute</span></span>|<span data-ttu-id="40c94-115">描述</span><span class="sxs-lookup"><span data-stu-id="40c94-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="40c94-116">一个字符串，定义用于传出通道的连接池的名称。</span><span class="sxs-lookup"><span data-stu-id="40c94-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="40c94-117">在流处理模式中，不共享连接，这意味着禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="40c94-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="40c94-118">默认值为字符串 "default"。</span><span class="sxs-lookup"><span data-stu-id="40c94-118">The default is a "default" string.</span></span> <span data-ttu-id="40c94-119">可以修改此值，以便将特定客户端的连接隔离到不同的组中。</span><span class="sxs-lookup"><span data-stu-id="40c94-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="40c94-120">一个值为正的 <xref:System.TimeSpan>，指定连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="40c94-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="40c94-121">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="40c94-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="40c94-122">一个 <xref:System.TimeSpan>，指定在关闭活动连接之前所要经过的时间。</span><span class="sxs-lookup"><span data-stu-id="40c94-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="40c94-123">默认值为 00:05:00。</span><span class="sxs-lookup"><span data-stu-id="40c94-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="40c94-124">连接在返回到连接缓存之后关闭，而不是在活动传输期间关闭。</span><span class="sxs-lookup"><span data-stu-id="40c94-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="40c94-125">TCP 传输使用的连接缓存将根据需要为每一个终结点创建新连接，直至达到 `maxOutboundConnectionsPerEndpoint.` 所设置的缓存限制。</span><span class="sxs-lookup"><span data-stu-id="40c94-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="40c94-126">一个正整数，指定由服务启动的与远程终结点的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="40c94-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="40c94-127">超出此限制的连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="40c94-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="40c94-128">`idleTimeout` 限制连接在引发异常前保持排队状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="40c94-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="40c94-129">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="40c94-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="40c94-130">此属性限制从客户端到特定服务终结点的同时活动的连接数。</span><span class="sxs-lookup"><span data-stu-id="40c94-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="40c94-131">如果由于具有更多的活动客户端连接而超出此值，则服务可能表现为对客户端无响应。</span><span class="sxs-lookup"><span data-stu-id="40c94-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="40c94-132">在此情况下，应调整此值使之超过与特定终结点的同时活动的最大预期客户端连接数。</span><span class="sxs-lookup"><span data-stu-id="40c94-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40c94-133">子元素</span><span class="sxs-lookup"><span data-stu-id="40c94-133">Child Elements</span></span>  
 <span data-ttu-id="40c94-134">无。</span><span class="sxs-lookup"><span data-stu-id="40c94-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40c94-135">父元素</span><span class="sxs-lookup"><span data-stu-id="40c94-135">Parent Elements</span></span>  
  
|<span data-ttu-id="40c94-136">元素</span><span class="sxs-lookup"><span data-stu-id="40c94-136">Element</span></span>|<span data-ttu-id="40c94-137">描述</span><span class="sxs-lookup"><span data-stu-id="40c94-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40c94-138">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="40c94-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="40c94-139">定义传输，该传输使通道使用命名管道传输消息。</span><span class="sxs-lookup"><span data-stu-id="40c94-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40c94-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="40c94-140">See also</span></span>
- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="40c94-141">传输</span><span class="sxs-lookup"><span data-stu-id="40c94-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="40c94-142">选择传输</span><span class="sxs-lookup"><span data-stu-id="40c94-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="40c94-143">绑定</span><span class="sxs-lookup"><span data-stu-id="40c94-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="40c94-144">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="40c94-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="40c94-145">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="40c94-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="40c94-146">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="40c94-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
