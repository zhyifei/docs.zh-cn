---
title: '&lt;webSocketSettings&gt;'
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 134a233a337c40d21f7547fe385ec788cef2165b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150053"
---
# <a name="ltwebsocketsettingsgt"></a><span data-ttu-id="80b4a-102">&lt;webSocketSettings&gt;</span><span class="sxs-lookup"><span data-stu-id="80b4a-102">&lt;webSocketSettings&gt;</span></span>
<span data-ttu-id="80b4a-103">用来指定 Web Socket 设置的配置元素。</span><span class="sxs-lookup"><span data-stu-id="80b4a-103">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="80b4a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="80b4a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="80b4a-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="80b4a-105">\<bindings></span></span>  
<span data-ttu-id="80b4a-106">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="80b4a-106">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80b4a-107">语法</span><span class="sxs-lookup"><span data-stu-id="80b4a-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80b4a-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="80b4a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="80b4a-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="80b4a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80b4a-110">特性</span><span class="sxs-lookup"><span data-stu-id="80b4a-110">Attributes</span></span>  
  
|<span data-ttu-id="80b4a-111">特性</span><span class="sxs-lookup"><span data-stu-id="80b4a-111">Attribute</span></span>|<span data-ttu-id="80b4a-112">描述</span><span class="sxs-lookup"><span data-stu-id="80b4a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80b4a-113">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="80b4a-113">createNotificationOnConnection</span></span>|<span data-ttu-id="80b4a-114">指定是否在连接时发送通知。</span><span class="sxs-lookup"><span data-stu-id="80b4a-114">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="80b4a-115">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="80b4a-115">disablePayloadMasking</span></span>|<span data-ttu-id="80b4a-116">指定是否禁用 Web Socket 掩码。</span><span class="sxs-lookup"><span data-stu-id="80b4a-116">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="80b4a-117">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="80b4a-117">keepAliveInterval</span></span>|<span data-ttu-id="80b4a-118">指定保持活动状态的间隔。</span><span class="sxs-lookup"><span data-stu-id="80b4a-118">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="80b4a-119">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="80b4a-119">maxPendingConnections</span></span>|<span data-ttu-id="80b4a-120">指定服务上等待调度的最大连接数。</span><span class="sxs-lookup"><span data-stu-id="80b4a-120">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="80b4a-121">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="80b4a-121">receiveBufferSize</span></span>|<span data-ttu-id="80b4a-122">指定接收缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="80b4a-122">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="80b4a-123">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="80b4a-123">sendBufferSize</span></span>|<span data-ttu-id="80b4a-124">指定发送缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="80b4a-124">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="80b4a-125">subProtocol</span><span class="sxs-lookup"><span data-stu-id="80b4a-125">subProtocol</span></span>|<span data-ttu-id="80b4a-126">指定 Web Socket 子协议。</span><span class="sxs-lookup"><span data-stu-id="80b4a-126">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="80b4a-127">transportUsage</span><span class="sxs-lookup"><span data-stu-id="80b4a-127">transportUsage</span></span>|<span data-ttu-id="80b4a-128">指定何时使用 Web Socket。</span><span class="sxs-lookup"><span data-stu-id="80b4a-128">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="80b4a-129">transportUsage 特性</span><span class="sxs-lookup"><span data-stu-id="80b4a-129">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="80b4a-130">值</span><span class="sxs-lookup"><span data-stu-id="80b4a-130">Value</span></span>|<span data-ttu-id="80b4a-131">描述</span><span class="sxs-lookup"><span data-stu-id="80b4a-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="80b4a-132">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="80b4a-132">WhenDuplex</span></span>|<span data-ttu-id="80b4a-133">如果为双工协定，则使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="80b4a-133">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="80b4a-134">Always</span><span class="sxs-lookup"><span data-stu-id="80b4a-134">Always</span></span>|<span data-ttu-id="80b4a-135">始终使用 Web Socket 协议，而不管协定类型。</span><span class="sxs-lookup"><span data-stu-id="80b4a-135">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="80b4a-136">Never</span><span class="sxs-lookup"><span data-stu-id="80b4a-136">Never</span></span>|<span data-ttu-id="80b4a-137">永远不使用 Web Socket 协议。</span><span class="sxs-lookup"><span data-stu-id="80b4a-137">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80b4a-138">子元素</span><span class="sxs-lookup"><span data-stu-id="80b4a-138">Child Elements</span></span>  
 <span data-ttu-id="80b4a-139">无</span><span class="sxs-lookup"><span data-stu-id="80b4a-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80b4a-140">父元素</span><span class="sxs-lookup"><span data-stu-id="80b4a-140">Parent Elements</span></span>  
  
|<span data-ttu-id="80b4a-141">元素</span><span class="sxs-lookup"><span data-stu-id="80b4a-141">Element</span></span>|<span data-ttu-id="80b4a-142">描述</span><span class="sxs-lookup"><span data-stu-id="80b4a-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="80b4a-143">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="80b4a-143">\<netHttpBinding></span></span>|<span data-ttu-id="80b4a-144">指定 NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="80b4a-144">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="80b4a-145">示例</span><span class="sxs-lookup"><span data-stu-id="80b4a-145">Example</span></span>  
 <span data-ttu-id="80b4a-146">下面的示例演示如何使用\<webSocketSettings > 元素。</span><span class="sxs-lookup"><span data-stu-id="80b4a-146">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="80b4a-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="80b4a-147">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 <xref:System.ServiceModel.Channels.BindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>  
 [<span data-ttu-id="80b4a-148">绑定</span><span class="sxs-lookup"><span data-stu-id="80b4a-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="80b4a-149">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="80b4a-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="80b4a-150">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="80b4a-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="80b4a-151">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="80b4a-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
