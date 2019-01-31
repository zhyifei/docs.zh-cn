---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 76b8a0feaf51b39c9c988d853db7e3bf96244905
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55284578"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="48308-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="48308-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="48308-102">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="48308-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="48308-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="48308-103">\<system.serviceModel></span></span>  
<span data-ttu-id="48308-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="48308-104">\<bindings></span></span>  
<span data-ttu-id="48308-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="48308-105">\<customBinding></span></span>  
<span data-ttu-id="48308-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="48308-106">\<binding></span></span>  
<span data-ttu-id="48308-107">\<namePipeTransport></span><span class="sxs-lookup"><span data-stu-id="48308-107">\<namePipeTransport></span></span>  
<span data-ttu-id="48308-108">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="48308-108">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48308-109">语法</span><span class="sxs-lookup"><span data-stu-id="48308-109">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48308-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48308-110">Attributes and Elements</span></span>  
 <span data-ttu-id="48308-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="48308-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48308-112">特性</span><span class="sxs-lookup"><span data-stu-id="48308-112">Attributes</span></span>  
  
|<span data-ttu-id="48308-113">特性</span><span class="sxs-lookup"><span data-stu-id="48308-113">Attribute</span></span>|<span data-ttu-id="48308-114">描述</span><span class="sxs-lookup"><span data-stu-id="48308-114">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="48308-115">一个字符串，定义用于传出通道的连接池的名称。</span><span class="sxs-lookup"><span data-stu-id="48308-115">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="48308-116">在流处理模式中，不共享连接，这意味着禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="48308-116">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="48308-117">默认值为字符串 "default"。</span><span class="sxs-lookup"><span data-stu-id="48308-117">The default is a "default" string.</span></span> <span data-ttu-id="48308-118">可以修改此值，以便将特定客户端的连接隔离到不同的组中。</span><span class="sxs-lookup"><span data-stu-id="48308-118">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="48308-119">一个值为正的 <xref:System.TimeSpan>，指定连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="48308-119">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="48308-120">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="48308-120">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="48308-121">一个正整数，指定由服务启动的与远程终结点的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="48308-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="48308-122">超出此限制的连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="48308-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="48308-123">`idleTimeout` 限制连接在引发异常前保持排队状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="48308-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="48308-124">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="48308-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="48308-125">此属性限制从客户端到特定服务终结点的同时活动的连接数。</span><span class="sxs-lookup"><span data-stu-id="48308-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="48308-126">如果由于具有更多的活动客户端连接而超出此值，则服务可能表现为对客户端无响应。</span><span class="sxs-lookup"><span data-stu-id="48308-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="48308-127">在此情况下，应调整此值使之超过与特定终结点的同时活动的最大预期客户端连接数。</span><span class="sxs-lookup"><span data-stu-id="48308-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48308-128">子元素</span><span class="sxs-lookup"><span data-stu-id="48308-128">Child Elements</span></span>  
 <span data-ttu-id="48308-129">无。</span><span class="sxs-lookup"><span data-stu-id="48308-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48308-130">父元素</span><span class="sxs-lookup"><span data-stu-id="48308-130">Parent Elements</span></span>  
  
|<span data-ttu-id="48308-131">元素</span><span class="sxs-lookup"><span data-stu-id="48308-131">Element</span></span>|<span data-ttu-id="48308-132">描述</span><span class="sxs-lookup"><span data-stu-id="48308-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48308-133">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="48308-133">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="48308-134">定义传输，该传输使通道使用命名管道传输消息。</span><span class="sxs-lookup"><span data-stu-id="48308-134">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48308-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="48308-135">See also</span></span>
- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="48308-136">传输</span><span class="sxs-lookup"><span data-stu-id="48308-136">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="48308-137">选择传输</span><span class="sxs-lookup"><span data-stu-id="48308-137">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="48308-138">绑定</span><span class="sxs-lookup"><span data-stu-id="48308-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="48308-139">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="48308-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="48308-140">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="48308-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="48308-141">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="48308-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
