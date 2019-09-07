---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400471"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="a3b81-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="a3b81-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="a3b81-102">指定命名管道绑定的其他连接池设置。</span><span class="sxs-lookup"><span data-stu-id="a3b81-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
<span data-ttu-id="a3b81-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3b81-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a3b81-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a3b81-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a3b81-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a3b81-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a3b81-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="a3b81-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="a3b81-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="a3b81-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a3b81-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedPipeTransport >** ](namedpipetransport.md)</span><span class="sxs-lookup"><span data-stu-id="a3b81-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)</span></span>\
<span data-ttu-id="a3b81-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionPoolSettings >**</span><span class="sxs-lookup"><span data-stu-id="a3b81-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b81-110">语法</span><span class="sxs-lookup"><span data-stu-id="a3b81-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3b81-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a3b81-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a3b81-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a3b81-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3b81-113">特性</span><span class="sxs-lookup"><span data-stu-id="a3b81-113">Attributes</span></span>  
  
|<span data-ttu-id="a3b81-114">特性</span><span class="sxs-lookup"><span data-stu-id="a3b81-114">Attribute</span></span>|<span data-ttu-id="a3b81-115">描述</span><span class="sxs-lookup"><span data-stu-id="a3b81-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="a3b81-116">一个字符串，定义用于传出通道的连接池的名称。</span><span class="sxs-lookup"><span data-stu-id="a3b81-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="a3b81-117">在流处理模式中，不共享连接，这意味着禁用连接池。</span><span class="sxs-lookup"><span data-stu-id="a3b81-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="a3b81-118">默认值为字符串 "default"。</span><span class="sxs-lookup"><span data-stu-id="a3b81-118">The default is a "default" string.</span></span> <span data-ttu-id="a3b81-119">可以修改此值，以便将特定客户端的连接隔离到不同的组中。</span><span class="sxs-lookup"><span data-stu-id="a3b81-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="a3b81-120">一个值为正的 <xref:System.TimeSpan>，指定连接在断开前可以空闲的最长时间。</span><span class="sxs-lookup"><span data-stu-id="a3b81-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="a3b81-121">默认值为 00:02:00。</span><span class="sxs-lookup"><span data-stu-id="a3b81-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="a3b81-122">一个正整数，指定由服务启动的与远程终结点的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="a3b81-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="a3b81-123">超出此限制的连接需要排队，直到连接数低于限制值。</span><span class="sxs-lookup"><span data-stu-id="a3b81-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="a3b81-124">`idleTimeout` 限制连接在引发异常前保持排队状态的持续时间。</span><span class="sxs-lookup"><span data-stu-id="a3b81-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="a3b81-125">默认值为 10。</span><span class="sxs-lookup"><span data-stu-id="a3b81-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="a3b81-126">此属性限制从客户端到特定服务终结点的同时活动的连接数。</span><span class="sxs-lookup"><span data-stu-id="a3b81-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="a3b81-127">如果由于具有更多的活动客户端连接而超出此值，则服务可能表现为对客户端无响应。</span><span class="sxs-lookup"><span data-stu-id="a3b81-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="a3b81-128">在此情况下，应调整此值使之超过与特定终结点的同时活动的最大预期客户端连接数。</span><span class="sxs-lookup"><span data-stu-id="a3b81-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3b81-129">子元素</span><span class="sxs-lookup"><span data-stu-id="a3b81-129">Child Elements</span></span>  
 <span data-ttu-id="a3b81-130">无。</span><span class="sxs-lookup"><span data-stu-id="a3b81-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3b81-131">父元素</span><span class="sxs-lookup"><span data-stu-id="a3b81-131">Parent Elements</span></span>  
  
|<span data-ttu-id="a3b81-132">元素</span><span class="sxs-lookup"><span data-stu-id="a3b81-132">Element</span></span>|<span data-ttu-id="a3b81-133">描述</span><span class="sxs-lookup"><span data-stu-id="a3b81-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3b81-134">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="a3b81-134">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="a3b81-135">定义传输，该传输使通道使用命名管道传输消息。</span><span class="sxs-lookup"><span data-stu-id="a3b81-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a3b81-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3b81-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a3b81-137">传输</span><span class="sxs-lookup"><span data-stu-id="a3b81-137">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="a3b81-138">选择传输</span><span class="sxs-lookup"><span data-stu-id="a3b81-138">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="a3b81-139">绑定</span><span class="sxs-lookup"><span data-stu-id="a3b81-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a3b81-140">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="a3b81-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a3b81-141">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="a3b81-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a3b81-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a3b81-142">\<customBinding></span></span>](custombinding.md)
