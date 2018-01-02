---
title: "&lt;tcpTransport&gt; 的 &lt;connectionPoolSettings&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f0e9c4d34caa16f41e874b7a3880325a6585c230
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltconnectionpoolsettingsgt-of-lttcptransportgt"></a><span data-ttu-id="14e31-102">&lt;tcpTransport&gt; 的 &lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="14e31-102">&lt;connectionPoolSettings&gt; of &lt;tcpTransport&gt;</span></span>
<span data-ttu-id="14e31-103">指定 TCP 传输的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="14e31-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="14e31-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="14e31-104">\<system.serviceModel></span></span>  
<span data-ttu-id="14e31-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="14e31-105">\<bindings></span></span>  
<span data-ttu-id="14e31-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="14e31-106">\<customBinding></span></span>  
<span data-ttu-id="14e31-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="14e31-107">\<binding></span></span>  
<span data-ttu-id="14e31-108">\<tcpTransport ></span><span class="sxs-lookup"><span data-stu-id="14e31-108">\<tcpTransport></span></span>  
<span data-ttu-id="14e31-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="14e31-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14e31-110">语法</span><span class="sxs-lookup"><span data-stu-id="14e31-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
    groupName="String"  
    idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14e31-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="14e31-111">Attributes and Elements</span></span>  
 <span data-ttu-id="14e31-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="14e31-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14e31-113">特性</span><span class="sxs-lookup"><span data-stu-id="14e31-113">Attributes</span></span>  
  
|<span data-ttu-id="14e31-114">特性</span><span class="sxs-lookup"><span data-stu-id="14e31-114">Attribute</span></span>|<span data-ttu-id="14e31-115">描述</span><span class="sxs-lookup"><span data-stu-id="14e31-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="14e31-116">一个字符串，定义用于传出通道的连接池的名称。</span><span class="sxs-lookup"><span data-stu-id="14e31-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="14e31-117">在流处理模式中，不共享连接，这意味着禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="14e31-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="14e31-118">默认值为字符串 "default"。</span><span class="sxs-lookup"><span data-stu-id="14e31-118">The default is a "default" string.</span></span> <span data-ttu-id="14e31-119">可以修改此值，以便将特定客户端的连接隔离到不同的组中。</span><span class="sxs-lookup"><span data-stu-id="14e31-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="14e31-120">一个值为正的 <xref:System.TimeSpan>，指定连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="14e31-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="14e31-121">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="14e31-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="14e31-122">一个 <xref:System.TimeSpan>，指定在关闭活动连接之前所要经过的时间。</span><span class="sxs-lookup"><span data-stu-id="14e31-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="14e31-123">默认值为 00:05:00。</span><span class="sxs-lookup"><span data-stu-id="14e31-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="14e31-124">连接在返回到连接缓存之后关闭，而不是在活动传输期间关闭。</span><span class="sxs-lookup"><span data-stu-id="14e31-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="14e31-125">TCP 传输使用的连接缓存将根据需要为每一个终结点创建新连接，直至达到 `maxOutboundConnectionsPerEndpoint.` 所设置的缓存限制。</span><span class="sxs-lookup"><span data-stu-id="14e31-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="14e31-126">一个正整数，指定由服务启动的与远程终结点的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="14e31-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="14e31-127">超出此限制的连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="14e31-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="14e31-128">`idleTimeout` 限制连接在引发异常前保持排队状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="14e31-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="14e31-129">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="14e31-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="14e31-130">此属性限制从客户端到特定服务终结点的同时活动的连接数。</span><span class="sxs-lookup"><span data-stu-id="14e31-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="14e31-131">如果由于具有更多的活动客户端连接而超出此值，则服务可能表现为对客户端无响应。</span><span class="sxs-lookup"><span data-stu-id="14e31-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="14e31-132">在此情况下，应调整此值使之超过与特定终结点的同时活动的最大预期客户端连接数。</span><span class="sxs-lookup"><span data-stu-id="14e31-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14e31-133">子元素</span><span class="sxs-lookup"><span data-stu-id="14e31-133">Child Elements</span></span>  
 <span data-ttu-id="14e31-134">无。</span><span class="sxs-lookup"><span data-stu-id="14e31-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14e31-135">父元素</span><span class="sxs-lookup"><span data-stu-id="14e31-135">Parent Elements</span></span>  
  
|<span data-ttu-id="14e31-136">元素</span><span class="sxs-lookup"><span data-stu-id="14e31-136">Element</span></span>|<span data-ttu-id="14e31-137">描述</span><span class="sxs-lookup"><span data-stu-id="14e31-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14e31-138">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="14e31-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="14e31-139">定义传输，该传输使通道使用命名管道传输消息。</span><span class="sxs-lookup"><span data-stu-id="14e31-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14e31-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="14e31-140">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="14e31-141">传输</span><span class="sxs-lookup"><span data-stu-id="14e31-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="14e31-142">选择传输</span><span class="sxs-lookup"><span data-stu-id="14e31-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="14e31-143">绑定</span><span class="sxs-lookup"><span data-stu-id="14e31-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="14e31-144">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="14e31-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="14e31-145">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="14e31-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="14e31-146">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="14e31-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
