---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 80784f40130e572ae374bd9b26e701360dbfcaa5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399135"
---
# <a name="websocketsettings"></a><span data-ttu-id="a4f56-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="a4f56-101">\<webSocketSettings></span></span>
<span data-ttu-id="a4f56-102">用来指定 Web Socket 设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="a4f56-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="a4f56-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a4f56-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a4f56-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a4f56-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a4f56-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a4f56-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="a4f56-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="a4f56-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="a4f56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="a4f56-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="a4f56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<s >**</span><span class="sxs-lookup"><span data-stu-id="a4f56-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4f56-109">语法</span><span class="sxs-lookup"><span data-stu-id="a4f56-109">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a4f56-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a4f56-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a4f56-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a4f56-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a4f56-112">特性</span><span class="sxs-lookup"><span data-stu-id="a4f56-112">Attributes</span></span>  
  
|<span data-ttu-id="a4f56-113">特性</span><span class="sxs-lookup"><span data-stu-id="a4f56-113">Attribute</span></span>|<span data-ttu-id="a4f56-114">描述</span><span class="sxs-lookup"><span data-stu-id="a4f56-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a4f56-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="a4f56-115">createNotificationOnConnection</span></span>|<span data-ttu-id="a4f56-116">指定是否在连接时发送通知。</span><span class="sxs-lookup"><span data-stu-id="a4f56-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="a4f56-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="a4f56-117">disablePayloadMasking</span></span>|<span data-ttu-id="a4f56-118">指定是否禁用 Web Socket 掩码。</span><span class="sxs-lookup"><span data-stu-id="a4f56-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="a4f56-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="a4f56-119">keepAliveInterval</span></span>|<span data-ttu-id="a4f56-120">指定保持活动状态的间隔。</span><span class="sxs-lookup"><span data-stu-id="a4f56-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="a4f56-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="a4f56-121">maxPendingConnections</span></span>|<span data-ttu-id="a4f56-122">指定服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="a4f56-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="a4f56-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="a4f56-123">receiveBufferSize</span></span>|<span data-ttu-id="a4f56-124">指定接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="a4f56-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="a4f56-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="a4f56-125">sendBufferSize</span></span>|<span data-ttu-id="a4f56-126">指定发送缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="a4f56-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="a4f56-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="a4f56-127">subProtocol</span></span>|<span data-ttu-id="a4f56-128">指定 Web Socket 子协议。</span><span class="sxs-lookup"><span data-stu-id="a4f56-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="a4f56-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="a4f56-129">transportUsage</span></span>|<span data-ttu-id="a4f56-130">指定何时使用 Web Socket。</span><span class="sxs-lookup"><span data-stu-id="a4f56-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="a4f56-131">transportUsage 特性</span><span class="sxs-lookup"><span data-stu-id="a4f56-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="a4f56-132">值</span><span class="sxs-lookup"><span data-stu-id="a4f56-132">Value</span></span>|<span data-ttu-id="a4f56-133">描述</span><span class="sxs-lookup"><span data-stu-id="a4f56-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a4f56-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="a4f56-134">WhenDuplex</span></span>|<span data-ttu-id="a4f56-135">如果为双工协定，则使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="a4f56-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="a4f56-136">Always</span><span class="sxs-lookup"><span data-stu-id="a4f56-136">Always</span></span>|<span data-ttu-id="a4f56-137">始终使用 Web Socket 协议，而不管协定类型。</span><span class="sxs-lookup"><span data-stu-id="a4f56-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="a4f56-138">Never</span><span class="sxs-lookup"><span data-stu-id="a4f56-138">Never</span></span>|<span data-ttu-id="a4f56-139">永远不使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="a4f56-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a4f56-140">子元素</span><span class="sxs-lookup"><span data-stu-id="a4f56-140">Child Elements</span></span>  
 <span data-ttu-id="a4f56-141">无</span><span class="sxs-lookup"><span data-stu-id="a4f56-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a4f56-142">父元素</span><span class="sxs-lookup"><span data-stu-id="a4f56-142">Parent Elements</span></span>  
  
|<span data-ttu-id="a4f56-143">元素</span><span class="sxs-lookup"><span data-stu-id="a4f56-143">Element</span></span>|<span data-ttu-id="a4f56-144">描述</span><span class="sxs-lookup"><span data-stu-id="a4f56-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a4f56-145">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="a4f56-145">\<netHttpBinding></span></span>|<span data-ttu-id="a4f56-146">指定 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="a4f56-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a4f56-147">示例</span><span class="sxs-lookup"><span data-stu-id="a4f56-147">Example</span></span>  
 <span data-ttu-id="a4f56-148">下面的示例演示如何使用\<s > 元素。</span><span class="sxs-lookup"><span data-stu-id="a4f56-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="a4f56-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4f56-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="a4f56-150">绑定</span><span class="sxs-lookup"><span data-stu-id="a4f56-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a4f56-151">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="a4f56-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="a4f56-152">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="a4f56-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="a4f56-153">\<binding></span><span class="sxs-lookup"><span data-stu-id="a4f56-153">\<binding></span></span>](../../../misc/binding.md)
