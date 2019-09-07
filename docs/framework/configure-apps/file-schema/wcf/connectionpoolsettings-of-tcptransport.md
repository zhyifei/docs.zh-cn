---
title: <connectionPoolSettings> 的 <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398096"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="55a12-102">\<connectionPoolSettings > \<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="55a12-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="55a12-103">指定 TCP 传输的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="55a12-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
<span data-ttu-id="55a12-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="55a12-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="55a12-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="55a12-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="55a12-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="55a12-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="55a12-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="55a12-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="55a12-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="55a12-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="55a12-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tcpTransport >** ](tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="55a12-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)</span></span>\
<span data-ttu-id="55a12-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionPoolSettings >**</span><span class="sxs-lookup"><span data-stu-id="55a12-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a12-111">语法</span><span class="sxs-lookup"><span data-stu-id="55a12-111">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="55a12-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="55a12-112">Attributes and Elements</span></span>  
 <span data-ttu-id="55a12-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="55a12-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="55a12-114">特性</span><span class="sxs-lookup"><span data-stu-id="55a12-114">Attributes</span></span>  
  
|<span data-ttu-id="55a12-115">特性</span><span class="sxs-lookup"><span data-stu-id="55a12-115">Attribute</span></span>|<span data-ttu-id="55a12-116">描述</span><span class="sxs-lookup"><span data-stu-id="55a12-116">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="55a12-117">一个字符串，定义用于传出通道的连接池的名称。</span><span class="sxs-lookup"><span data-stu-id="55a12-117">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="55a12-118">在流处理模式中，不共享连接，这意味着禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="55a12-118">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="55a12-119">默认值为字符串 "default"。</span><span class="sxs-lookup"><span data-stu-id="55a12-119">The default is a "default" string.</span></span> <span data-ttu-id="55a12-120">可以修改此值，以便将特定客户端的连接隔离到不同的组中。</span><span class="sxs-lookup"><span data-stu-id="55a12-120">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="55a12-121">一个值为正的 <xref:System.TimeSpan>，指定连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="55a12-121">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="55a12-122">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="55a12-122">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="55a12-123">一个 <xref:System.TimeSpan>，指定在关闭活动连接之前所要经过的时间。</span><span class="sxs-lookup"><span data-stu-id="55a12-123">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="55a12-124">默认值为 00:05:00。</span><span class="sxs-lookup"><span data-stu-id="55a12-124">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="55a12-125">连接在返回到连接缓存之后关闭，而不是在活动传输期间关闭。</span><span class="sxs-lookup"><span data-stu-id="55a12-125">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="55a12-126">TCP 传输使用的连接缓存将根据需要为每一个终结点创建新连接，直至达到 `maxOutboundConnectionsPerEndpoint.` 所设置的缓存限制。</span><span class="sxs-lookup"><span data-stu-id="55a12-126">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="55a12-127">一个正整数，指定由服务启动的与远程终结点的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="55a12-127">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="55a12-128">超出此限制的连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="55a12-128">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="55a12-129">`idleTimeout` 限制连接在引发异常前保持排队状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="55a12-129">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="55a12-130">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="55a12-130">The default is 10.</span></span><br /><br /> <span data-ttu-id="55a12-131">此属性限制从客户端到特定服务终结点的同时活动的连接数。</span><span class="sxs-lookup"><span data-stu-id="55a12-131">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="55a12-132">如果由于具有更多的活动客户端连接而超出此值，则服务可能表现为对客户端无响应。</span><span class="sxs-lookup"><span data-stu-id="55a12-132">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="55a12-133">在此情况下，应调整此值使之超过与特定终结点的同时活动的最大预期客户端连接数。</span><span class="sxs-lookup"><span data-stu-id="55a12-133">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="55a12-134">子元素</span><span class="sxs-lookup"><span data-stu-id="55a12-134">Child Elements</span></span>  
 <span data-ttu-id="55a12-135">无。</span><span class="sxs-lookup"><span data-stu-id="55a12-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="55a12-136">父元素</span><span class="sxs-lookup"><span data-stu-id="55a12-136">Parent Elements</span></span>  
  
|<span data-ttu-id="55a12-137">元素</span><span class="sxs-lookup"><span data-stu-id="55a12-137">Element</span></span>|<span data-ttu-id="55a12-138">描述</span><span class="sxs-lookup"><span data-stu-id="55a12-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="55a12-139">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="55a12-139">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="55a12-140">定义传输，该传输使通道使用命名管道传输消息。</span><span class="sxs-lookup"><span data-stu-id="55a12-140">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55a12-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="55a12-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="55a12-142">传输</span><span class="sxs-lookup"><span data-stu-id="55a12-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="55a12-143">选择传输</span><span class="sxs-lookup"><span data-stu-id="55a12-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="55a12-144">绑定</span><span class="sxs-lookup"><span data-stu-id="55a12-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="55a12-145">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="55a12-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="55a12-146">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="55a12-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="55a12-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="55a12-147">\<customBinding></span></span>](custombinding.md)
