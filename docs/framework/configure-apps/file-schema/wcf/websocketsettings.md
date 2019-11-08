---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732555"
---
# <a name="websocketsettings"></a><span data-ttu-id="2e2f0-101">\<s ></span><span class="sxs-lookup"><span data-stu-id="2e2f0-101">\<webSocketSettings></span></span>
<span data-ttu-id="2e2f0-102">用来指定 Web Socket 设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="2e2f0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e2f0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e2f0-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="2e2f0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2e2f0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2e2f0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2e2f0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2e2f0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="2e2f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="2e2f0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2e2f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<s >**</span><span class="sxs-lookup"><span data-stu-id="2e2f0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e2f0-109">语法</span><span class="sxs-lookup"><span data-stu-id="2e2f0-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e2f0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2e2f0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e2f0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e2f0-112">特性</span><span class="sxs-lookup"><span data-stu-id="2e2f0-112">Attributes</span></span>  
  
|<span data-ttu-id="2e2f0-113">特性</span><span class="sxs-lookup"><span data-stu-id="2e2f0-113">Attribute</span></span>|<span data-ttu-id="2e2f0-114">描述</span><span class="sxs-lookup"><span data-stu-id="2e2f0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e2f0-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="2e2f0-115">createNotificationOnConnection</span></span>|<span data-ttu-id="2e2f0-116">指定是否在连接时发送通知。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="2e2f0-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="2e2f0-117">disablePayloadMasking</span></span>|<span data-ttu-id="2e2f0-118">指定是否禁用 Web Socket 掩码。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="2e2f0-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="2e2f0-119">keepAliveInterval</span></span>|<span data-ttu-id="2e2f0-120">指定保持活动状态的间隔。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="2e2f0-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="2e2f0-121">maxPendingConnections</span></span>|<span data-ttu-id="2e2f0-122">指定服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="2e2f0-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="2e2f0-123">receiveBufferSize</span></span>|<span data-ttu-id="2e2f0-124">指定接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="2e2f0-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="2e2f0-125">sendBufferSize</span></span>|<span data-ttu-id="2e2f0-126">指定发送缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="2e2f0-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="2e2f0-127">subProtocol</span></span>|<span data-ttu-id="2e2f0-128">指定 Web Socket 子协议。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="2e2f0-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="2e2f0-129">transportUsage</span></span>|<span data-ttu-id="2e2f0-130">指定何时使用 Web Socket。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="2e2f0-131">transportUsage 特性</span><span class="sxs-lookup"><span data-stu-id="2e2f0-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="2e2f0-132">“值”</span><span class="sxs-lookup"><span data-stu-id="2e2f0-132">Value</span></span>|<span data-ttu-id="2e2f0-133">描述</span><span class="sxs-lookup"><span data-stu-id="2e2f0-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e2f0-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="2e2f0-134">WhenDuplex</span></span>|<span data-ttu-id="2e2f0-135">如果为双工协定，则使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="2e2f0-136">Always</span><span class="sxs-lookup"><span data-stu-id="2e2f0-136">Always</span></span>|<span data-ttu-id="2e2f0-137">始终使用 Web Socket 协议，而不管协定类型。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="2e2f0-138">Never</span><span class="sxs-lookup"><span data-stu-id="2e2f0-138">Never</span></span>|<span data-ttu-id="2e2f0-139">永远不使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e2f0-140">子元素</span><span class="sxs-lookup"><span data-stu-id="2e2f0-140">Child Elements</span></span>  
 <span data-ttu-id="2e2f0-141">None</span><span class="sxs-lookup"><span data-stu-id="2e2f0-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e2f0-142">父元素</span><span class="sxs-lookup"><span data-stu-id="2e2f0-142">Parent Elements</span></span>  
  
|<span data-ttu-id="2e2f0-143">元素</span><span class="sxs-lookup"><span data-stu-id="2e2f0-143">Element</span></span>|<span data-ttu-id="2e2f0-144">描述</span><span class="sxs-lookup"><span data-stu-id="2e2f0-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2e2f0-145">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2e2f0-145">\<netHttpBinding></span></span>|<span data-ttu-id="2e2f0-146">指定 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2e2f0-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2e2f0-147">示例</span><span class="sxs-lookup"><span data-stu-id="2e2f0-147">Example</span></span>  
 <span data-ttu-id="2e2f0-148">下面的示例演示如何使用 \<s > 元素。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2e2f0-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e2f0-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="2e2f0-150">绑定</span><span class="sxs-lookup"><span data-stu-id="2e2f0-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2e2f0-151">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="2e2f0-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2e2f0-152">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="2e2f0-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2e2f0-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="2e2f0-153">\<binding></span></span>](bindings.md)
