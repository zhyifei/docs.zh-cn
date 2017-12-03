---
title: '&lt;connectionPoolSettings&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f1980365da8514060290066a4e15e5f88e35f7f4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltconnectionpoolsettingsgt"></a><span data-ttu-id="d8b98-102">&lt;connectionPoolSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="d8b98-102">&lt;connectionPoolSettings&gt;</span></span>
<span data-ttu-id="d8b98-103">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="d8b98-103">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
 <span data-ttu-id="d8b98-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d8b98-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d8b98-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d8b98-105">\<bindings></span></span>  
<span data-ttu-id="d8b98-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d8b98-106">\<customBinding></span></span>  
<span data-ttu-id="d8b98-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="d8b98-107">\<binding></span></span>  
<span data-ttu-id="d8b98-108">\<namePipeTransport ></span><span class="sxs-lookup"><span data-stu-id="d8b98-108">\<namePipeTransport></span></span>  
<span data-ttu-id="d8b98-109">\<connectionPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="d8b98-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b98-110">语法</span><span class="sxs-lookup"><span data-stu-id="d8b98-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings  
        groupName="String"  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8b98-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d8b98-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d8b98-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d8b98-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8b98-113">特性</span><span class="sxs-lookup"><span data-stu-id="d8b98-113">Attributes</span></span>  
  
|<span data-ttu-id="d8b98-114">特性</span><span class="sxs-lookup"><span data-stu-id="d8b98-114">Attribute</span></span>|<span data-ttu-id="d8b98-115">描述</span><span class="sxs-lookup"><span data-stu-id="d8b98-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="d8b98-116">一个字符串，定义用于传出通道的连接池的名称。</span><span class="sxs-lookup"><span data-stu-id="d8b98-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="d8b98-117">在流处理模式中，不共享连接，这意味着禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="d8b98-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="d8b98-118">默认值为字符串 "default"。</span><span class="sxs-lookup"><span data-stu-id="d8b98-118">The default is a "default" string.</span></span> <span data-ttu-id="d8b98-119">可以修改此值，以便将特定客户端的连接隔离到不同的组中。</span><span class="sxs-lookup"><span data-stu-id="d8b98-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="d8b98-120">一个值为正的 <xref:System.TimeSpan>，指定连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="d8b98-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="d8b98-121">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="d8b98-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="d8b98-122">一个正整数，指定由服务启动的与远程终结点的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="d8b98-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="d8b98-123">超出此限制的连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="d8b98-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="d8b98-124">`idleTimeout` 限制连接在引发异常前保持排队状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="d8b98-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="d8b98-125">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="d8b98-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="d8b98-126">此属性限制从客户端到特定服务终结点的同时活动的连接数。</span><span class="sxs-lookup"><span data-stu-id="d8b98-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="d8b98-127">如果由于具有更多的活动客户端连接而超出此值，则服务可能表现为对客户端无响应。</span><span class="sxs-lookup"><span data-stu-id="d8b98-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="d8b98-128">在此情况下，应调整此值使之超过与特定终结点的同时活动的最大预期客户端连接数。</span><span class="sxs-lookup"><span data-stu-id="d8b98-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8b98-129">子元素</span><span class="sxs-lookup"><span data-stu-id="d8b98-129">Child Elements</span></span>  
 <span data-ttu-id="d8b98-130">无。</span><span class="sxs-lookup"><span data-stu-id="d8b98-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8b98-131">父元素</span><span class="sxs-lookup"><span data-stu-id="d8b98-131">Parent Elements</span></span>  
  
|<span data-ttu-id="d8b98-132">元素</span><span class="sxs-lookup"><span data-stu-id="d8b98-132">Element</span></span>|<span data-ttu-id="d8b98-133">描述</span><span class="sxs-lookup"><span data-stu-id="d8b98-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8b98-134">\<namedPipeTransport ></span><span class="sxs-lookup"><span data-stu-id="d8b98-134">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="d8b98-135">定义传输，该传输使通道使用命名管道传输消息。</span><span class="sxs-lookup"><span data-stu-id="d8b98-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d8b98-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8b98-136">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="d8b98-137">传输</span><span class="sxs-lookup"><span data-stu-id="d8b98-137">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [<span data-ttu-id="d8b98-138">选择传输</span><span class="sxs-lookup"><span data-stu-id="d8b98-138">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [<span data-ttu-id="d8b98-139">绑定</span><span class="sxs-lookup"><span data-stu-id="d8b98-139">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d8b98-140">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="d8b98-140">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="d8b98-141">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="d8b98-141">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="d8b98-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="d8b98-142">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
